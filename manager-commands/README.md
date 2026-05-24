# Engineering Manager Automation Toolkit

**100+ AI-powered prompts for engineering managers to automate daily operations, KPI tracking, engineer performance, team health, and Amazon-style business writing**

---

![Automation](https://img.shields.io/badge/automation-enabled-brightgreen)
![AI Powered](https://img.shields.io/badge/AI-powered-blue)
![Management](https://img.shields.io/badge/engineering-management-orange)
![Prompts](https://img.shields.io/badge/prompts-125%2B-purple)
![License](https://img.shields.io/badge/license-MIT-green)

---

## What This Is

This is a structured library of **125+ prompt templates** designed to be executed by AI agents (Claude, MeshClaw) on a recurring schedule. Each prompt pulls data from real engineering systems, synthesizes it into actionable intelligence, and delivers a formatted summary directly to the manager via Slack DM.

Instead of spending the first hour of every day context-switching across dashboards, code review tools, deployment pipelines, and ticketing systems, this toolkit does it for you. The result: a single morning briefing with everything you need to lead your team effectively.

**Key principles:**
- Zero manual effort after initial setup
- Data-driven decisions over gut feelings
- Proactive detection of risks before they escalate
- Consistent operating cadence regardless of meeting load

---

## Table of Contents

| # | Category | Count | Description |
|---|----------|-------|-------------|
| 1 | [Daily Reports](#daily-reports) | 10 | Morning ops, deployments, CR queues, blockers |
| 2 | [KPI Metrics](#kpi-metrics) | 10 | DORA metrics, cycle time, velocity, availability |
| 3 | [Engineer Performance](#engineer-performance) | 10 | Output, growth, review quality, risk flags |
| 4 | [Team Operations](#team-operations) | 10 | Dependencies, capacity, tech debt, compliance |
| 5 | [Communication](#communication) | 10 | Status emails, stakeholder updates, postmortems |
| 6 | [Planning](#planning) | 10 | Sprint prep, OKRs, roadmap, launch readiness |
| 7 | [Incidents](#incidents) | 10 | Active incidents, trends, SLA, alarm fatigue |
| 8 | [Hiring](#hiring) | 5 | Pipeline, interviews, onboarding |
| 9 | [1:1 Meetings](#11-meetings) | 10 | Prep, career growth, workload, recognition |
| 10 | [Process](#process) | 15 | Retros, meeting audits, knowledge silos, automation |
| 11 | [Amazon Writing](#amazon-writing) | 15 | QBR, WBR, YBR, PR/FAQ, 6-pagers, COE |
| 12 | [Customer Experience](#customer-experience) | 10 | CX metrics, voice of customer, journey maps |

**Total: 125 prompt templates**

---

## Daily Reports

Automated morning briefings that aggregate overnight activity into a single digestible summary.

- Deployment status across all environments
- Code review queue depth and aging
- Blocked tasks and dependency chains
- Oncall handoff notes and active alarms
- Sprint burndown trajectory

## KPI Metrics

Quantitative engineering health indicators calculated from real system data.

- DORA metrics (deployment frequency, lead time, change failure rate, MTTR)
- Cycle time from commit to production
- Sprint velocity trends over rolling 6 weeks
- Service availability and error budgets
- PR review latency percentiles

## Engineer Performance

Individual contributor tracking for growth coaching and performance calibration.

- Code output volume and complexity
- Review quality and thoroughness scores
- Mentorship and collaboration signals
- Technical debt contribution vs. reduction
- Risk flags for burnout or disengagement

## Team Operations

Cross-cutting operational awareness for the team as a unit.

- External dependency health and risk
- Capacity allocation vs. planned work
- Tech debt accumulation rate
- Compliance and security posture
- Tooling and infrastructure friction points

## Communication

Pre-drafted communications ready for review and send.

- Weekly status emails to leadership
- Stakeholder project updates
- Postmortem summaries and action items
- Cross-team coordination messages
- Escalation drafts with supporting data

## Planning

Forward-looking preparation for sprints, quarters, and launches.

- Sprint planning data packs
- OKR progress snapshots
- Roadmap dependency visualization
- Launch readiness checklists
- Resource planning scenarios

## Incidents

Real-time and historical incident intelligence.

- Active incident status and ownership
- Incident trend analysis over 30/60/90 days
- SLA compliance tracking
- Alarm fatigue detection
- Root cause pattern identification

## Hiring

Pipeline management and new hire integration tracking.

- Recruiting pipeline health
- Interview loop scheduling and feedback
- Onboarding progress and milestones
- Time-to-productivity metrics
- Offer acceptance rate trends

## 1:1 Meetings

Data-driven preparation for meaningful one-on-one conversations.

- Per-engineer context briefings
- Career growth trajectory analysis
- Workload balance assessment
- Recognition opportunity detection
- Follow-up item tracking

## Process

Team process health and continuous improvement opportunities.

- Retrospective insight aggregation
- Meeting time audit and optimization
- Knowledge silo detection
- Automation opportunity identification
- Process compliance adherence
- Toil measurement and reduction tracking

## Amazon Writing

Templates for Amazon's narrative-driven business documents.

- QBR (Quarterly Business Review) narratives
- WBR (Weekly Business Review) data packs
- YBR (Yearly Business Review) strategic summaries
- PR/FAQ documents for new initiatives
- 6-pager long-form proposals
- COE (Correction of Error) write-ups
- OP1/OP2 planning inputs

## Customer Experience

Customer-facing metrics and experience quality tracking.

- CX metric dashboards (CSAT, NPS proxies)
- Voice of customer signal aggregation
- Journey map friction point identification
- Feature adoption and engagement rates
- Support ticket trend analysis

---

## How It Works

```
+-----------------+     +------------+     +---------------------------+
|  Cron Scheduler | --> |  AI Agent  | --> |      Data Sources         |
|  (MeshClaw)     |     |  (Claude)  |     |  Email, Calendar, CRUX,  |
+-----------------+     +------------+     |  Taskei, Pipelines,      |
                              |            |  Apollo, Oncall           |
                              v            +---------------------------+
                     +------------------+
                     | Formatted Report |
                     +------------------+
                              |
                              v
                     +------------------+
                     |    Slack DM      |
                     +------------------+
```

**Integration points:**
- **CRUX** - Code review status, CR aging, review assignments
- **Taskei** - Task tracking, sprint progress, blocked items
- **Pipelines** - Deployment status, pipeline health, stage failures
- **Apollo** - Deployment targets, environment status, rollback state
- **Oncall** - Active alarms, ticket volume, escalation paths
- **Email/Calendar** - Meeting load, action items, follow-ups

**AI Agents:**
- **Claude Code** - Prompt execution, data synthesis, report generation
- **MeshClaw** - Scheduled automation, cron-based triggering, delivery

---

## Quick Start

1. Clone this repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/manager-prompts.git
   ```

2. Browse prompts by category in the `prompts/` directory or see [INDEX.md](INDEX.md) for a flat listing.

3. Configure your AI agent to execute prompts on a schedule (see Cron Schedule below).

4. Set up Slack webhook for delivery:
   ```bash
   export SLACK_WEBHOOK_URL="https://hooks.slack.com/services/YOUR/WEBHOOK/URL"
   ```

5. Run your first prompt manually to verify integration:
   ```bash
   claude --prompt prompts/daily/morning-ops-briefing.md
   ```

---

## Cron Schedule

Recommended automated cadence:

| Time | Frequency | Prompt Category | Purpose |
|------|-----------|----------------|---------|
| 7:00 AM | Daily | Morning Ops Briefing | Start-of-day context |
| 7:15 AM | Daily | CR Queue Status | Unblock reviews early |
| 8:00 AM | Mon/Wed/Fri | KPI Dashboard | Track trending metrics |
| 9:00 AM | Mon | Sprint Health Check | Week planning context |
| 4:00 PM | Fri | Weekly Status Draft | Pre-write weekend email |
| 9:00 AM | 1st of month | Monthly Metrics Roll-up | Leadership reporting |
| 10:00 AM | Quarterly | QBR Narrative Draft | Business review prep |

---

## Example Output

A typical morning Slack DM delivery:

```
--------------------------------------------------
MORNING OPS BRIEFING | 2026-05-24 (Saturday)
--------------------------------------------------

[Deployments]
  - service-alpha: deployed v2.41.0 to prod (03:22 UTC) - healthy
  - service-beta: pipeline BLOCKED at integration-test stage
    Action: test-owner@ investigating flaky test in LoginFlowTest

[Code Reviews]
  - 3 CRs aging >48h (2 from engineer-a, 1 from engineer-b)
  - 7 CRs awaiting your review (oldest: 18h)
  - Recommended: prioritize CR-12345 (blocks launch task)

[Blockers]
  - Task-9876: blocked on external team response (3 days)
    Action: escalation draft prepared (see thread)
  - Task-5432: blocked on security review approval
    Action: pinged security-team channel

[Oncall]
  - 2 alarms fired overnight (both auto-resolved)
  - Current oncall: engineer-c (day 3 of 7)
  - Ticket volume: normal (4 tickets, avg resolution 22min)

[Sprint Progress]
  - Day 7 of 10 | 68% complete | On track
  - Risk: 2 stories not yet started (assigned to engineer-d)
--------------------------------------------------
```

---

## Built With

| Tool | Role |
|------|------|
| [Claude](https://www.anthropic.com/claude) | AI agent for prompt execution and data synthesis |
| [MeshClaw](https://w.amazon.com/bin/view/MeshClaw/) | Cron scheduling and automated task orchestration |
| [CRUX](https://docs.hub.amazon.dev/crux/) | Code review data |
| [Taskei](https://w.amazon.com/bin/view/Taskei/) | Task and sprint tracking |
| [Pipelines](https://docs.hub.amazon.dev/pipelines/) | Deployment pipeline status |
| [Apollo](https://docs.hub.amazon.dev/apollo/) | Deployment and environment state |

---

## Repository Structure

```
manager-prompts/
├── README.md              # This file
├── LICENSE                # MIT License
├── ARCHITECTURE.md        # System design overview
├── CATEGORIES.md          # Detailed category breakdown
├── INDEX.md               # Flat index for AI ingestion
├── .github/
│   └── FUNDING.yml        # Sponsorship configuration
└── prompts/
    ├── daily/             # 10 daily operation prompts
    ├── kpi/               # 10 KPI metric prompts
    ├── performance/       # 10 engineer performance prompts
    ├── operations/        # 10 team operations prompts
    ├── communication/     # 10 communication prompts
    ├── planning/          # 10 planning prompts
    ├── incidents/         # 10 incident management prompts
    ├── hiring/            # 5 hiring prompts
    ├── one-on-ones/       # 10 1:1 meeting prompts
    ├── process/           # 15 process improvement prompts
    ├── amazon-writing/    # 15 Amazon narrative prompts
    └── customer-experience/ # 10 CX prompts
```

---

## Contributing

Contributions welcome. Each prompt should:
1. Have a clear, single purpose
2. Specify its data source requirements
3. Define its output format
4. Include a sample output

---

## License

MIT License - see [LICENSE](LICENSE) for details.

Copyright (c) 2024-2026
