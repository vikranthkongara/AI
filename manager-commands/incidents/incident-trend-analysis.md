# Incident Trend Analysis

Analyze monthly incident trends including frequency, severity distribution, repeat offenders, time-of-day patterns, and improvement trajectory.

## Data Sources
- Oncall system (historical incidents, resolution times, severity data)
- Pipelines (deployment correlation data)
- Apollo (rollback history)
- Taskei (COE action items, improvement tasks)
- CRUX CRs (fix commits linked to incidents)

## Instructions
1. Query the oncall system for all incidents from the past 30 days involving team-owned services. Also pull 60 and 90 day data for trend comparison.
2. Calculate frequency metrics:
   - Total incidents this month vs previous months
   - Incidents per week trend
   - Incidents per service
3. Analyze severity distribution:
   - Count by severity level (Sev1 through Sev5)
   - Compare distribution to previous months
   - Calculate mean time to detect (MTTD) and mean time to resolve (MTTR) by severity
4. Identify repeat offenders:
   - Services with the most incidents
   - Same root cause appearing multiple times
   - Alarms that fire repeatedly for the same underlying issue
5. Analyze time-of-day patterns:
   - When do most incidents occur? (business hours vs off-hours)
   - Day-of-week distribution
   - Correlation with deployment windows
6. Analyze deployment correlation:
   - What percentage of incidents occurred within 6 hours of a deployment?
   - Which services have the highest deployment-to-incident ratio?
7. Check resolution patterns:
   - Most common mitigation actions (rollback, config change, scaling, restart)
   - Incidents that required escalation beyond the team
   - Incidents that breached SLA response times
8. Check Taskei for COE action items and their completion status - are we addressing root causes?

## Output Format
```
## Incident Trend Analysis
**Period:** [Month Year]
**Compared Against:** [Previous 2 months]

### Executive Summary
- Total incidents: [N] (vs [N-1] last month, [N-2] two months ago)
- Trend: [Improving / Stable / Worsening]
- Most concerning pattern: [Brief description]

### Frequency Trends
| Month | Total | Sev1 | Sev2 | Sev3 | Sev4-5 | Trend |
|-------|-------|------|------|------|--------|-------|
| [Current] | [N] | [N] | [N] | [N] | [N] | [Arrow] |
| [Previous] | [N] | [N] | [N] | [N] | [N] | |
| [2 months ago] | [N] | [N] | [N] | [N] | [N] | |

### Resolution Metrics
| Metric | This Month | Last Month | Target | Status |
|--------|-----------|------------|--------|--------|
| MTTD (Sev1-2) | [X min] | [Y min] | [Z min] | [Met/Missed] |
| MTTR (Sev1-2) | [X min] | [Y min] | [Z min] | [Met/Missed] |
| MTTD (Sev3+) | [X min] | [Y min] | [Z min] | [Met/Missed] |
| MTTR (Sev3+) | [X min] | [Y min] | [Z min] | [Met/Missed] |

### Repeat Offenders (Services)
| Service | Incidents This Month | Last Month | Root Causes | Action Needed |
|---------|---------------------|------------|-------------|---------------|

### Repeat Root Causes
| Root Cause Category | Count | Services Affected | Prevention Status |
|--------------------|-------|-------------------|-------------------|

### Time-of-Day Heatmap
| Hour Block | Mon | Tue | Wed | Thu | Fri | Sat | Sun |
|-----------|-----|-----|-----|-----|-----|-----|-----|
| 00-04 | [N] | [N] | [N] | [N] | [N] | [N] | [N] |
| 04-08 | [N] | [N] | [N] | [N] | [N] | [N] | [N] |
| 08-12 | [N] | [N] | [N] | [N] | [N] | [N] | [N] |
| 12-16 | [N] | [N] | [N] | [N] | [N] | [N] | [N] |
| 16-20 | [N] | [N] | [N] | [N] | [N] | [N] | [N] |
| 20-24 | [N] | [N] | [N] | [N] | [N] | [N] | [N] |

### Deployment Correlation
- Incidents within 6hrs of deployment: [X]% ([N] of [Total])
- Highest-risk deployment windows: [Times]
- Services with highest deploy-incident ratio: [List]

### Mitigation Action Breakdown
| Action Type | Count | % | Avg Time to Apply |
|------------|-------|---|-------------------|
| Rollback | [N] | [X]% | [Y min] |
| Config change | [N] | [X]% | [Y min] |
| Scaling | [N] | [X]% | [Y min] |
| Restart | [N] | [X]% | [Y min] |
| Code fix | [N] | [X]% | [Y min] |

### COE Action Item Progress
- Total action items from this month's incidents: [N]
- Completed: [N]
- In progress: [N]
- Overdue: [N]

### Recommendations
1. [Specific recommendation based on trends]
2. [Specific recommendation based on repeat offenders]
3. [Specific recommendation based on time patterns]
```

## Delivery
Send the full report as a Slack DM to me on the 1st of each month. Include a brief 3-line summary suitable for including in monthly business reviews.
