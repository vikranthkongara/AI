# Roadmap Progress Check

Assess progress against the quarterly roadmap by checking milestone completion, identifying at-risk deliverables, and suggesting timeline adjustments.

## Data Sources
- Taskei (epics, milestones, task completion rates)
- CRUX CRs (recent merge activity indicating progress)
- Pipelines (deployment frequency as a proxy for delivery velocity)
- Calendar (upcoming deadlines, review meetings)
- Email/Outlook (stakeholder communications about timeline changes)

## Instructions
1. Query Taskei for all epics and milestones tagged with the current quarter's roadmap label.
2. For each roadmap item, calculate:
   - Percentage of tasks completed vs total tasks
   - Percentage of story points completed vs total estimated
   - Burn-down trajectory (on track, ahead, behind)
3. Check CRUX for recent CR activity on roadmap-related packages to validate reported progress.
4. Check Pipelines for deployment activity on related services to confirm code is actually shipping.
5. For items that are behind schedule:
   - Calculate days of slippage
   - Identify root causes (scope creep, blocked dependencies, resource constraints)
   - Suggest corrective actions (scope reduction, resource reallocation, timeline extension)
6. Check email for any stakeholder communications that indicate external timeline pressures or changes.
7. Flag any roadmap items with less than 50% completion that are past 50% of the quarter.

## Output Format
```
## Quarterly Roadmap Progress - Q[X] [Year]
**Report Date:** [Date]
**Quarter Progress:** [X]% through quarter ([days remaining] days left)

### Summary
- On Track: [N] items
- At Risk: [N] items
- Behind: [N] items
- Completed: [N] items

### Detailed Status

#### [Roadmap Item 1]
- **Owner:** [Engineer/Team]
- **Status:** [On Track / At Risk / Behind / Completed]
- **Progress:** [X]% complete ([Y/Z] tasks, [A/B] story points)
- **Key Milestone:** [Next milestone] due [date]
- **Recent Activity:** [Summary of recent CRs and deployments]
- **Risk Level:** [Low/Medium/High]
- **Notes:** [Any blockers or concerns]

[Repeat for each item]

### At-Risk Items Requiring Attention
| Item | Days Behind | Root Cause | Recommended Action |
|------|-------------|------------|-------------------|

### Timeline Adjustment Recommendations
- [Specific suggestions for re-planning]

### Dependencies & External Blockers
- [List any cross-team or external dependencies affecting progress]
```

## Delivery
Send the full report as a Slack DM to me every Monday morning. If any item transitions from "On Track" to "At Risk" or "Behind" mid-week, send an immediate alert via Slack DM.
