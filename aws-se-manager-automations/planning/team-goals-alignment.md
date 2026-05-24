# Team Goals Alignment Check

Verify that individual engineer goals are aligned with team and organizational objectives, identify gaps or misalignments, and suggest corrections.

## Data Sources
- Taskei (individual goal documents, team OKRs, org-level priorities)
- CRUX CRs (actual work being done vs stated goals)
- Calendar (1:1 meetings, goal review sessions)
- Email/Outlook (goal-setting communications, org priority announcements)

## Instructions
1. Query Taskei for each team member's documented individual goals for the current period (half/year).
2. Query Taskei for team-level OKRs and organizational priorities.
3. For each team member, map their individual goals to team/org objectives:
   - Which team OKR does each goal support?
   - Are there team OKRs with no individual goals mapped to them?
   - Are there individual goals that don't connect to any team objective?
4. Check actual work output (CRUX CRs, Taskei task completion) against stated goals:
   - Is the engineer spending time on work aligned with their goals?
   - Are there significant efforts not captured in any goal?
   - Are goals being actively progressed or stagnant?
5. Identify alignment gaps:
   - Team objectives with insufficient individual goal coverage
   - Individual goals that are orthogonal to team direction
   - Engineers whose day-to-day work diverges significantly from their goals
6. Check for goal quality:
   - Are goals measurable (specific metrics or deliverables)?
   - Are goals appropriately scoped (achievable but stretching)?
   - Do goals cover both delivery and growth dimensions?
7. Identify upcoming 1:1s or goal review sessions from the calendar where misalignments should be discussed.

## Output Format
```
## Team Goals Alignment Report
**Date:** [Date]
**Period:** [H1/H2 Year]
**Team Members:** [N]

### Alignment Matrix
| Engineer | Goal 1 -> [OKR] | Goal 2 -> [OKR] | Goal 3 -> [OKR] | Alignment Score |
|----------|-----------------|-----------------|-----------------|-----------------|

Alignment Score: Strong / Moderate / Weak / Misaligned

### Team OKR Coverage
| Team OKR | Individual Goals Mapped | Engineers Contributing | Coverage |
|----------|----------------------|----------------------|----------|
| [OKR 1]  | [N] goals            | [Names]              | [Good/Gap] |
| [OKR 2]  | [N] goals            | [Names]              | [Good/Gap] |

### Coverage Gaps (OKRs without sufficient goal support)
| Team OKR | Current Coverage | Recommended Action |
|----------|-----------------|-------------------|

### Orphan Goals (Not mapped to team OKRs)
| Engineer | Goal | Possible Mapping | Recommendation |
|----------|------|-----------------|----------------|

### Work-Goal Divergence
| Engineer | Goal Focus | Actual Work Focus | Divergence Level | Notes |
|----------|-----------|-------------------|-----------------|-------|

### Goal Quality Issues
| Engineer | Goal | Issue | Suggestion |
|----------|------|-------|-----------|
[Goals that are too vague, not measurable, or inappropriately scoped]

### Recommended 1:1 Discussion Topics
| Engineer | Next 1:1 Date | Topics to Discuss |
|----------|--------------|-------------------|

### Summary
- Engineers fully aligned: [N]
- Engineers needing minor adjustments: [N]
- Engineers needing significant realignment: [N]
- Team OKRs fully covered: [N/Total]
```

## Delivery
Send the full report as a Slack DM to me at the start of each month. Also send a reminder before each goal review period (mid-year, year-end) with specific talking points for each engineer's 1:1.
