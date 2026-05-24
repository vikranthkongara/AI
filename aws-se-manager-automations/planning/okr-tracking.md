# OKR Tracking Report

Check OKR progress by measuring key results against targets, assessing confidence levels, and identifying corrective actions needed to stay on track.

## Data Sources
- Taskei (OKR-tagged epics and tasks, completion metrics)
- Pipelines (deployment metrics for delivery-related KRs)
- Oncall system (operational metrics for reliability KRs)
- CRUX CRs (throughput metrics for productivity KRs)
- Email/Outlook (stakeholder updates on cross-team OKRs)

## Instructions
1. Query Taskei for all items tagged with current quarter OKR labels. Map tasks to their respective Objectives and Key Results.
2. For each Key Result, determine the measurement method:
   - **Delivery KRs:** Check task completion rates, deployment frequency from Pipelines
   - **Quality KRs:** Check incident rates from oncall system, rollback frequency from Pipelines
   - **Productivity KRs:** Check CR throughput from CRUX, cycle time from Taskei
   - **Hiring KRs:** Check headcount progress from Taskei hiring tasks
   - **Cross-team KRs:** Check email for partner team status updates
3. Calculate current value vs target for each KR:
   - Current measured value
   - Target value
   - Percentage achieved
   - Required run-rate to hit target by end of quarter
4. Assign confidence levels:
   - **High (Green):** On track or ahead, no blockers
   - **Medium (Yellow):** Slightly behind but recoverable with focused effort
   - **Low (Red):** Significantly behind, requires intervention or scope change
5. For Yellow and Red KRs, identify:
   - Root cause of the gap
   - Specific corrective actions
   - Resources or decisions needed
   - Whether the target should be revised
6. Check if any KRs have dependencies on other teams and verify those dependencies are on track.

## Output Format
```
## OKR Progress Report - Q[X] [Year]
**Report Date:** [Date]
**Quarter Progress:** [X]% through quarter

### Executive Summary
- Objectives on track: [N/Total]
- Key Results on track: [N/Total]
- Key Results at risk: [N]
- Key Results off track: [N]

### Objective 1: [Objective Statement]
**Overall Confidence:** [High/Medium/Low]

| Key Result | Target | Current | % Achieved | Run Rate Needed | Confidence |
|-----------|--------|---------|------------|-----------------|------------|
| KR 1.1    | [X]    | [Y]     | [Z]%       | [rate/week]     | [H/M/L]    |
| KR 1.2    | [X]    | [Y]     | [Z]%       | [rate/week]     | [H/M/L]    |

[Repeat for each Objective]

### At-Risk Key Results (Yellow)
| KR | Gap | Root Cause | Corrective Action | Owner |
|----|-----|-----------|-------------------|-------|

### Off-Track Key Results (Red)
| KR | Gap | Root Cause | Recommended Intervention | Decision Needed |
|----|-----|-----------|-------------------------|-----------------|

### Cross-Team Dependencies
| KR | Dependency | Partner Team | Their Status | Risk |
|----|-----------|--------------|--------------|------|

### Recommended Actions for This Week
1. [Prioritized action item]
2. [Prioritized action item]
```

## Delivery
Send the full report as a Slack DM to me every Monday morning. If any KR drops from Green to Yellow or Yellow to Red, send an immediate alert. Include a brief summary suitable for copy-pasting into leadership updates.
