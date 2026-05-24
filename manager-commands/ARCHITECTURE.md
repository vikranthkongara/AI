# Architecture Overview

This document describes how the Engineering Manager Automation Toolkit connects prompts to data sources, schedules execution, and delivers results.

---

## System Diagram

```
┌─────────────────────────────────────────────────────────────────────────┐
│                         SCHEDULING LAYER                                 │
│                                                                          │
│   ┌──────────────┐         ┌──────────────┐         ┌──────────────┐   │
│   │  Daily Cron  │         │ Weekly Cron  │         │ Monthly Cron │   │
│   │  (7:00 AM)   │         │  (Monday)    │         │  (1st)       │   │
│   └──────┬───────┘         └──────┬───────┘         └──────┬───────┘   │
│          │                        │                        │            │
└──────────┼────────────────────────┼────────────────────────┼────────────┘
           │                        │                        │
           v                        v                        v
┌─────────────────────────────────────────────────────────────────────────┐
│                         EXECUTION LAYER                                   │
│                                                                          │
│   ┌──────────────────────────────────────────────────────────────────┐  │
│   │                     AI Agent (Claude Code)                        │  │
│   │                                                                    │  │
│   │  1. Receives prompt template                                       │  │
│   │  2. Queries data sources via tools/APIs                            │  │
│   │  3. Synthesizes data into structured report                        │  │
│   │  4. Formats output for delivery                                    │  │
│   └──────────────────────────────────┬───────────────────────────────┘  │
│                                      │                                   │
└──────────────────────────────────────┼───────────────────────────────────┘
                                       │
           ┌───────────────────────────┼───────────────────────────┐
           │                           │                           │
           v                           v                           v
┌────────────────────┐   ┌────────────────────┐   ┌────────────────────┐
│    DATA SOURCES    │   │    DATA SOURCES    │   │    DATA SOURCES    │
│                    │   │                    │   │                    │
│  - Email (Outlook) │   │  - CRUX (CRs)     │   │  - Oncall (alarms) │
│  - Calendar        │   │  - Taskei (tasks)  │   │  - CloudWatch      │
│  - Quip docs       │   │  - Pipelines       │   │  - Sev tracker     │
│                    │   │  - Apollo (deploy)  │   │  - SLA dashboard   │
└────────────────────┘   └────────────────────┘   └────────────────────┘
                                       │
                                       v
                          ┌────────────────────┐
                          │  FORMATTED REPORT  │
                          │                    │
                          │  Structured text   │
                          │  with sections,    │
                          │  action items,     │
                          │  and risk flags    │
                          └─────────┬──────────┘
                                    │
                                    v
                          ┌────────────────────┐
                          │    DELIVERY        │
                          │                    │
                          │  Slack DM to       │
                          │  engineering       │
                          │  manager           │
                          └────────────────────┘
```

---

## Components

### 1. Cron Scheduler (MeshClaw)

MeshClaw provides the scheduling backbone. Each prompt is registered as a recurring task with:
- **Schedule**: cron expression (e.g., `0 7 * * 1-5` for weekday mornings)
- **Prompt path**: reference to the prompt template file
- **Agent config**: which AI agent to invoke
- **Delivery target**: Slack channel or DM

### 2. AI Agent (Claude Code)

Claude Code executes each prompt by:
1. Reading the prompt template to understand what data is needed
2. Using MCP tools to query relevant data sources
3. Applying the synthesis logic defined in the prompt
4. Formatting the output according to the template's delivery format
5. Returning the structured report for delivery

### 3. Data Sources

| Source | Protocol | Data Provided |
|--------|----------|---------------|
| CRUX | MCP Tool | Code reviews, CR status, reviewer assignments |
| Taskei | MCP Tool | Tasks, sprints, blockers, story points |
| Pipelines | MCP Tool | Pipeline health, stage status, failures |
| Apollo | MCP Tool | Deployment status, environment health |
| Oncall | MCP Tool | Alarms, tickets, escalations |
| Email | API | Action items, follow-ups, thread summaries |
| Calendar | API | Meeting load, scheduling conflicts |

### 4. Delivery (Slack DM)

Reports are delivered as formatted Slack messages using Block Kit for rich formatting:
- Section headers for visual scanning
- Action item callouts
- Risk flag highlighting
- Links to relevant systems for drill-down

---

## Data Flow Example

For a "Morning Ops Briefing" prompt:

```
1. MeshClaw triggers at 7:00 AM weekdays
2. Claude Code receives prompt: prompts/daily/morning-ops-briefing.md
3. Agent queries:
   - Pipelines: deployments in last 12 hours
   - CRUX: CRs aging > 24 hours
   - Taskei: blocked tasks
   - Oncall: overnight alarms
   - Pipelines: sprint burndown data
4. Agent synthesizes into structured briefing
5. Formatted message posted to manager's Slack DM
6. Total execution time: ~30 seconds
```

---

## Design Decisions

- **Prompt-as-code**: Each prompt is a version-controlled markdown file, enabling review, iteration, and collaboration.
- **Separation of concerns**: Scheduling, execution, data access, and delivery are independent layers.
- **Idempotent execution**: Any prompt can be re-run safely without side effects.
- **Graceful degradation**: If a data source is unavailable, the report includes what it can and flags the gap.
- **Human-in-the-loop**: Reports are informational. No automated actions are taken without explicit approval.
