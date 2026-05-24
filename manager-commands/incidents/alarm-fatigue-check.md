# Alarm Fatigue Check

Analyze oncall paging patterns to identify noisy alarms, duplicate alerts, auto-resolving alarms, and provide tuning recommendations to reduce alarm fatigue.

## Data Sources
- Oncall system (page history, alarm configurations, acknowledgment times)
- Apollo (service health metrics, alarm thresholds)
- Taskei (alarm tuning tasks, operational improvement tickets)
- Slack DMs (oncall handoff notes mentioning noisy alarms)

## Instructions
1. Query the oncall system for all pages in the last 30 days for team-owned services. Collect:
   - Alarm name, service, severity
   - Timestamp, duration until acknowledgment
   - Duration until resolution
   - Whether it auto-resolved (resolved without human action within 15 minutes)
   - Whether manual action was required
2. Identify noisy alarms:
   - Alarms that fired > 5 times in a week
   - Alarms that fire at the same time every day (scheduled-job related)
   - Alarms with > 50% auto-resolve rate (threshold may be too sensitive)
3. Identify duplicate/redundant alerts:
   - Multiple alarms that fire simultaneously for the same root cause
   - Alarms that always fire in a predictable sequence (cascade)
   - Different alarm names monitoring the same underlying metric
4. Analyze page timing:
   - Pages during sleeping hours (midnight to 6 AM) - were they actionable?
   - Weekend pages - were they truly urgent?
   - Pages during deployment windows that auto-resolved after bake
5. Calculate alarm fatigue metrics:
   - Total pages per oncall shift
   - Signal-to-noise ratio (actionable pages / total pages)
   - Average acknowledgment time (increasing ack time suggests fatigue)
   - Pages per engineer per week
6. For each noisy alarm, recommend tuning:
   - Adjust threshold (with suggested new value based on historical data)
   - Add suppression during known maintenance windows
   - Convert from page to ticket (if low-urgency)
   - Consolidate with related alarms
   - Add auto-remediation
7. Compare current month's page volume to previous months to identify trends.

## Output Format
```
## Alarm Fatigue Analysis
**Period:** Last 30 days
**Total Pages:** [N]
**Actionable Pages:** [N] ([X]%)
**Signal-to-Noise Ratio:** [X:1]

### Key Metrics
| Metric | Current | Last Month | Target | Status |
|--------|---------|------------|--------|--------|
| Pages per oncall shift | [N] | [N] | <[X] | [Met/Missed] |
| Auto-resolve rate | [X]% | [Y]% | <[Z]% | [Met/Missed] |
| Avg ack time | [X min] | [Y min] | <[Z min] | [Met/Missed] |
| Off-hours actionable % | [X]% | [Y]% | >[Z]% | [Met/Missed] |

### Top Noisy Alarms (Tune Immediately)
| Alarm | Service | Fires/Week | Auto-Resolve % | Actionable % | Recommendation |
|-------|---------|-----------|----------------|--------------|----------------|
| [Name] | [Svc] | [N] | [X]% | [Y]% | [Tune/Suppress/Demote] |

### Duplicate/Redundant Alert Groups
| Group | Alarms Involved | Root Trigger | Recommendation |
|-------|----------------|--------------|----------------|
| [Group 1] | [Alarm A, Alarm B, Alarm C] | [Common cause] | [Consolidate into single alarm] |

### Auto-Resolving Alarms (> 50% auto-resolve)
| Alarm | Service | Total Fires | Auto-Resolved | Suggested Threshold Change |
|-------|---------|-------------|---------------|---------------------------|

### Off-Hours Page Analysis
| Time Window | Total Pages | Actionable | Non-Actionable | Top Offenders |
|-------------|-------------|-----------|----------------|---------------|
| Midnight-6AM | [N] | [N] | [N] | [Alarm names] |
| Weekends | [N] | [N] | [N] | [Alarm names] |

### Page Load by Engineer (Last Rotation)
| Engineer | Total Pages | Off-Hours | Actionable % | Notes |
|----------|-------------|-----------|--------------|-------|

### Trending
| Month | Total Pages | Actionable % | Avg/Shift | Trend |
|-------|-------------|--------------|-----------|-------|

### Recommended Tuning Actions (Prioritized)
| Priority | Alarm | Action | Expected Reduction | Effort |
|----------|-------|--------|-------------------|--------|
| 1 | [Name] | [Specific tuning action] | -[N] pages/week | [Low/Med/High] |
| 2 | [Name] | [Specific tuning action] | -[N] pages/week | [Low/Med/High] |

### Estimated Impact of All Recommendations
- Current pages per shift: [N]
- Projected pages per shift after tuning: [N]
- Reduction: [X]%

### Taskei Tasks to Create
| Alarm | Tuning Action | Suggested Assignee | Priority |
|-------|--------------|-------------------|----------|
```

## Delivery
Send the full report as a Slack DM to me on the 1st and 15th of each month. Send an immediate alert if pages per shift exceed 2x the target for 3 consecutive days.
