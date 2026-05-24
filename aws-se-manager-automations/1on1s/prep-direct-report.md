# 1:1 Prep for Direct Report

Prepare a comprehensive briefing for an upcoming 1:1 meeting with a direct report, covering their recent work, blockers, goals progress, and suggested discussion points.

## Data Sources
- Taskei: Active tasks, recently completed tasks, blocked tasks for the engineer
- CRUX CRs: Code reviews authored and reviewed in the last 2 weeks
- Slack DMs: Recent messages between me and the engineer, any flagged topics
- Calendar: Previous 1:1 meeting notes, upcoming commitments
- Pipelines: Recent deployments they owned
- Apollo: Deployment status of their services
- Oncall system: Recent oncall shifts, pages received, incidents handled

## Instructions
1. Query Taskei for all tasks assigned to {{ENGINEER_NAME}} in the current sprint and last sprint. Note completion rate, any tasks marked blocked, and tasks that have been in-progress for more than 5 days.
2. Pull CRUX CRs authored by {{ENGINEER_NAME}} in the last 14 days. Note: number of CRs, average time to approval, any CRs with extended review cycles or contentious comments.
3. Pull CRUX CRs where {{ENGINEER_NAME}} was a reviewer. Note review turnaround time and thoroughness.
4. Check Slack DMs and relevant team channels for any topics they raised, questions asked, or blockers mentioned in the last 2 weeks.
5. Review my calendar notes from our last 1:1. Extract any action items I committed to and any follow-ups they mentioned.
6. Check Pipelines and Apollo for any deployments they drove. Note successes and any rollbacks or issues.
7. Check oncall system for any shifts they covered recently, pages received, and how they were resolved.
8. Cross-reference their current work against their quarterly goals (from Taskei) to assess progress.
9. Identify 3-5 suggested discussion topics based on all the above data.

## Output Format
```
## 1:1 Prep: {{ENGINEER_NAME}} - {{DATE}}

### Recent Accomplishments
- [List of completed tasks, shipped CRs, successful deployments]

### Current Work
- [Active tasks with status and estimated completion]

### Blockers & Concerns
- [Blocked tasks, stalled CRs, raised issues]

### Goals Progress
| Goal | Status | Notes |
|------|--------|-------|
| ... | On Track / At Risk / Behind | ... |

### Follow-ups from Last 1:1
- [Action items and their status]

### Suggested Discussion Topics
1. [Topic with context on why it's relevant]
2. ...

### Oncall & Operational Load
- [Recent shifts, incidents, load assessment]
```

## Delivery
Send the formatted report as a Slack DM to me at least 1 hour before the scheduled 1:1 meeting time (check calendar for the meeting).
