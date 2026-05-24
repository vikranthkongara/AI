# Project Milestone Check

Verify project milestones against planned dates, identify slippage, and calculate schedule risk for all active projects the team owns.

## Data Sources
- Taskei (milestones, due dates, task dependencies, epic timelines)
- CRUX CRs (code activity indicating progress toward milestones)
- Pipelines (deployment gates and release schedules)
- Calendar (review meetings, launch dates, external deadlines)
- Email/Outlook (stakeholder communications about date commitments)

## Instructions
1. Query Taskei for all active projects with defined milestones. Pull:
   - Milestone name and description
   - Planned completion date
   - Current status (tasks completed vs remaining)
   - Blocking dependencies
2. For each milestone, assess actual progress:
   - Check CRUX for related CRs: are they merged, in review, or not yet created?
   - Check Pipelines for deployment status: has code been promoted through stages?
   - Calculate the critical path: what sequence of tasks must complete for the milestone?
3. Calculate schedule risk:
   - **Days of buffer:** Planned date minus projected completion (based on current velocity)
   - **Risk score:** Based on buffer days, dependency count, and historical accuracy
   - **Slip probability:** High/Medium/Low based on patterns
4. For milestones with negative buffer (already slipping):
   - Calculate exact days of slippage
   - Identify the bottleneck tasks/engineers
   - Determine if the slip cascades to downstream milestones
5. Check calendar and email for any externally committed dates (customer launches, partner integrations, leadership reviews) that create hard deadlines.
6. Generate an early warning for milestones that are within 2 weeks of their date but less than 80% complete.

## Output Format
```
## Project Milestone Status Report
**Date:** [Date]

### Summary Dashboard
| Status | Count |
|--------|-------|
| On Track (Green) | [N] |
| At Risk (Yellow) | [N] |
| Slipping (Red) | [N] |
| Completed | [N] |

### Milestone Details

#### Project: [Project Name]

| Milestone | Planned Date | Projected Date | Buffer | Status | Owner |
|-----------|-------------|----------------|--------|--------|-------|
| [M1]      | [Date]      | [Date]         | [+/- days] | [G/Y/R] | [Name] |
| [M2]      | [Date]      | [Date]         | [+/- days] | [G/Y/R] | [Name] |

**Critical Path:** [Task A] -> [Task B] -> [Task C]
**Blockers:** [Any active blockers]

[Repeat for each project]

### Slipping Milestones (Immediate Attention)
| Project | Milestone | Days Behind | Bottleneck | Cascade Impact | Recommended Action |
|---------|-----------|-------------|------------|----------------|-------------------|

### Early Warnings (< 2 weeks out, < 80% complete)
| Project | Milestone | Due Date | Completion % | Gap Analysis |
|---------|-----------|----------|--------------|--------------|

### Hard Deadlines at Risk
| Deadline | Commitment To | Date | Dependent Milestone | Status |
|----------|--------------|------|--------------------|---------| 

### Recommendations
1. [Action item with urgency level]
2. [Action item with urgency level]
```

## Delivery
Send the full report as a Slack DM to me every Wednesday. Send immediate alerts for any milestone that transitions to "Slipping" status or when a hard deadline is at risk.
