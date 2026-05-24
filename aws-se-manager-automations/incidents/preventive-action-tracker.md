# Preventive Action Tracker

Track COE (Correction of Errors) and postmortem action items: completion rates, overdue items, recurring themes, and effectiveness of past actions.

## Data Sources
- Taskei (COE action items, improvement tasks, linked incidents)
- Oncall system (incident history, repeat incidents)
- CRUX CRs (code fixes implementing action items)
- Pipelines (infrastructure improvements deployed)
- Email/Outlook (COE review meeting notes, escalation threads)

## Instructions
1. Query Taskei for all tasks tagged as COE action items, postmortem follow-ups, or preventive actions. Collect:
   - Task ID, title, description
   - Source incident/COE
   - Priority and severity
   - Assignee
   - Due date
   - Current status (Not Started, In Progress, Done, Blocked)
   - Creation date
2. Calculate completion metrics:
   - Total action items (all time and last 90 days)
   - Completion rate (overall and by priority)
   - Average time from creation to completion
   - Items completed on time vs late
   - Currently overdue items
3. Identify overdue items:
   - List all items past their due date
   - Calculate days overdue
   - Determine if the source incident has recurred since the action was filed
   - Assess risk of each overdue item (what could happen if not done)
4. Analyze recurring themes:
   - Group action items by category (monitoring, testing, documentation, code fix, architecture)
   - Identify patterns (e.g., "we keep filing monitoring improvement actions but not completing them")
   - Check if the same type of action keeps appearing from different incidents
5. Assess effectiveness of completed actions:
   - For completed action items, did the related incident type stop recurring?
   - Were there incidents that occurred despite having a related action item completed?
   - Calculate preventive success rate
6. Check for blocked items:
   - What is blocking them? (dependency on another team, resource constraint, tech debt)
   - How long have they been blocked?
   - Can the blocker be escalated?
7. Check CRUX and Pipelines for in-progress work implementing action items.
8. Identify action items from high-severity incidents that are stalled.

## Output Format
```
## Preventive Action Tracker
**Date:** [Date]
**Total Open Action Items:** [N]
**Overdue Items:** [N] ([X]%)
**Completion Rate (90d):** [X]%

### Executive Summary
- On track: [N] items
- Overdue: [N] items (oldest: [X] days overdue)
- Blocked: [N] items
- High-severity incident actions overdue: [N] (CRITICAL)
- Recurring incidents with open actions: [N]

### Completion Metrics
| Metric | Last 30d | Last 90d | All Time | Target |
|--------|----------|----------|----------|--------|
| Total created | [N] | [N] | [N] | - |
| Completed | [N] | [N] | [N] | - |
| Completion rate | [X]% | [X]% | [X]% | >[Y]% |
| Avg time to complete | [X days] | [X days] | [X days] | <[Y days] |
| On-time completion | [X]% | [X]% | [X]% | >[Y]% |

### Overdue Action Items (Prioritized by Risk)
| Task ID | Title | Source Incident | Priority | Days Overdue | Assignee | Risk if Not Done |
|---------|-------|----------------|----------|--------------|----------|-----------------|
[Sorted by risk/priority]

### High-Severity Incident Actions (Sev1-2 Source)
| Task ID | Title | Source Incident | Status | Days Open | Assignee | Recurrence Risk |
|---------|-------|----------------|--------|-----------|----------|-----------------|

### Blocked Items
| Task ID | Title | Blocker | Days Blocked | Escalation Path | Recommendation |
|---------|-------|---------|--------------|-----------------|----------------|

### Recurring Themes
| Category | Open Items | Completed (90d) | Completion Rate | Concern |
|----------|-----------|-----------------|-----------------|---------|
| Monitoring gaps | [N] | [N] | [X]% | [High/Med/Low] |
| Test coverage | [N] | [N] | [X]% | [High/Med/Low] |
| Documentation | [N] | [N] | [X]% | [High/Med/Low] |
| Code fix | [N] | [N] | [X]% | [High/Med/Low] |
| Architecture | [N] | [N] | [X]% | [High/Med/Low] |
| Process | [N] | [N] | [X]% | [High/Med/Low] |

### Effectiveness Analysis
| Completed Action | Related Incidents Before | Related Incidents After | Effective? |
|-----------------|------------------------|----------------------|-----------|

### Incidents That Recurred Despite Open Actions
| Incident | Original Date | Recurrence Date | Related Action Item | Action Status |
|----------|--------------|-----------------|--------------------|--------------| 
[These are the most critical - we knew what to fix but didn't do it]

### In-Progress Work
| Task ID | Title | Assignee | CR Status | Pipeline Status | ETA |
|---------|-------|----------|-----------|-----------------|-----|

### Recommended Actions
1. [Most urgent: e.g., "Escalate blocked item X - source incident recurred twice"]
2. [Priority: e.g., "Reassign overdue item Y - current owner is at capacity"]
3. [Systemic: e.g., "Schedule a monitoring improvement sprint - 8 related items stuck"]

### Sprint Allocation Recommendation
Based on overdue items and risk, recommend allocating [X]% of next sprint capacity to preventive actions:
| Item | Priority | Effort | Justification |
|------|----------|--------|---------------|
```

## Delivery
Send the full report as a Slack DM to me every Monday. Send immediate alerts when a high-severity incident action item becomes overdue, or when an incident recurs and its associated action item is still open.
