# Weekly Output Summary

Per-engineer summary of weekly productivity: CRs authored/reviewed, tasks completed, deployments made, oncall pages handled, and overall contribution metrics.

## Data Sources
- **CRUX CRs**: Code reviews authored, reviewed, and merged per engineer
- **Taskei**: Tickets moved to Done, story points completed, tickets created
- **Pipelines/Apollo**: Deployments initiated per engineer
- **Oncall System**: Pages handled, incidents resolved
- **Calendar**: Working days available (subtract PTO, holidays)

## Instructions

1. **For each team member, gather weekly activity**:

   **Code Review Activity:**
   - CRs authored (count, total lines added/removed)
   - CRs merged (count)
   - CRs currently open/in review
   - CRs reviewed for others (count)
   - Review comments left on others' CRs (substantive vs style)
   - Average CR size

   **Task Completion:**
   - Taskei tickets moved to Done
   - Story points completed
   - Tickets moved to In Progress (new work started)
   - Bug fixes completed
   - Tickets carried over from previous week

   **Deployments:**
   - Production deployments initiated
   - Services deployed to
   - Any rollbacks triggered by their changes

   **Oncall (if applicable):**
   - Pages received and acknowledged
   - Incidents resolved
   - Time spent on oncall activities
   - Runbooks created or updated

   **Other Contributions:**
   - Design documents authored or reviewed
   - Mentoring activities (reviewing junior CRs, pairing sessions)
   - Documentation updates
   - Participation in team discussions

2. **Calculate normalized metrics**:
   - Output per available day (account for PTO, oncall reduction)
   - Week-over-week change
   - Comparison to personal 4-week average
   - Comparison to team average (anonymized in shared reports)

3. **Identify notable achievements**:
   - Particularly large or impactful CRs
   - Tickets completed ahead of schedule
   - Multi-service deployments
   - Successful incident resolution

4. **Flag potential concerns** (for manager's eyes only):
   - Significant drop in output vs personal average (>40% decline)
   - No CRs authored in the entire week
   - No reviews given (not contributing to team review load)
   - Working outside normal hours consistently (potential burnout)

## Output Format

```
# Weekly Output Summary - Week of [Date]

## Team Totals
- CRs merged: [count] | CRs reviewed: [count]
- Story points completed: [count]
- Production deployments: [count]
- Oncall pages handled: [count]
- Available engineer-days: [X] of [Y] possible

## Per-Engineer Summary

### [Engineer Name]
**Availability**: [X]/5 days (PTO: [dates if applicable])

| Metric | This Week | 4-Week Avg | Trend |
|--------|-----------|-----------|-------|
| CRs authored | [count] | [avg] | [arrow] |
| CRs merged | [count] | [avg] | [arrow] |
| Lines changed | [count] | [avg] | [arrow] |
| CRs reviewed | [count] | [avg] | [arrow] |
| Tickets completed | [count] | [avg] | [arrow] |
| Story points | [count] | [avg] | [arrow] |
| Deployments | [count] | [avg] | [arrow] |

**Highlights:**
- [Notable achievement or large piece of work completed]

**Oncall** (if on rotation): [X] pages, [Y] resolved, [Z] hours spent

---
(repeat for each engineer)

## Team Leaderboard (This Week)
- Most CRs merged: [name] ([count])
- Most reviews given: [name] ([count])
- Most story points: [name] ([count])
- Most deployments: [name] ([count])

## Flags for Manager Attention
- [Engineer A]: Output 50% below personal average - check in during 1:1
- [Engineer B]: No reviews given this week - remind about team review expectations
- [Engineer C]: On oncall - output expectedly lower, handled [X] pages effectively

## Week-over-Week Team Trend
- CRs merged: [this week] vs [last week] ([+/-X%])
- Points completed: [this week] vs [last week] ([+/-X%])
- Overall team output: [increasing/stable/decreasing]
```

## Delivery
- Send as Slack DM to me every Friday at 4:00 PM (end of week wrap-up)
- This report is for manager use only - do not share individual metrics with the team
- Use for 1:1 preparation and performance review evidence gathering
