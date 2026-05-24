# Oncall Load Balance Analysis

Analyze the distribution of oncall pages across team members to ensure fair distribution, identify overloaded individuals, and recommend rotation adjustments.

## Data Sources
- Oncall system (page history, rotation schedule, acknowledgment data)
- Calendar (PTO, holidays affecting rotation)
- Taskei (oncall improvement tasks)
- Slack DMs (oncall handoff notes, burden complaints)

## Instructions
1. Query the oncall system for all pages in the last 90 days. For each page, collect:
   - Page timestamp
   - Oncall engineer who received it
   - Severity
   - Time to acknowledge
   - Time to resolve
   - Whether it was off-hours (nights/weekends)
   - Whether it required extended engagement (> 30 minutes)
2. Calculate load distribution per engineer:
   - Total pages received
   - Off-hours pages received
   - High-severity pages received
   - Total incident response hours
   - Number of oncall shifts served
   - Pages per shift (normalized)
3. Calculate fairness metrics:
   - Standard deviation of pages across engineers
   - Gini coefficient of page distribution
   - Compare actual distribution to expected (even) distribution
   - Identify engineers > 1.5x the team average
   - Identify engineers < 0.5x the team average
4. Analyze factors contributing to imbalance:
   - Some shifts inherently noisier (day of week, time of month)
   - Service-specific pages going to the same person repeatedly
   - Rotation schedule creating systematic bias
   - PTO causing uneven shift coverage
5. Assess impact on individuals:
   - Sleep disruption score (off-hours pages, especially 12AM-6AM)
   - Sprint productivity impact (hours spent in incidents vs planned work)
   - Consecutive difficult shifts without relief
6. Check for burnout indicators:
   - Increasing acknowledgment times (fatigue signal)
   - Engineers who have been overloaded for multiple months
   - Engineers who haven't had a break from oncall in > 8 weeks
7. Generate rebalancing recommendations.

## Output Format
```
## Oncall Load Balance Report
**Period:** Last 90 days
**Team Size (Oncall Rotation):** [N] engineers
**Total Pages:** [N]
**Fairness Score:** [X]/100 (100 = perfectly even)

### Load Distribution Summary
| Engineer | Shifts | Total Pages | Off-Hours | Sev1-2 | Incident Hours | Pages/Shift | vs Average |
|----------|--------|-------------|-----------|--------|----------------|-------------|-----------|
| [Name] | [N] | [N] | [N] | [N] | [X hrs] | [N] | [+/-X%] |
[Sorted by pages/shift descending]

**Team Average:** [X] pages/shift
**Standard Deviation:** [Y]

### Fairness Analysis
| Metric | Value | Target | Status |
|--------|-------|--------|--------|
| Gini Coefficient | [X] | < 0.2 | [Fair/Unfair] |
| Max/Min Ratio | [X]:1 | < 2:1 | [Fair/Unfair] |
| Engineers > 1.5x avg | [N] | 0 | [Names] |
| Engineers < 0.5x avg | [N] | - | [Names] |

### Overloaded Engineers (Immediate Attention)
| Engineer | Pages/Shift | vs Average | Off-Hours % | Consecutive Heavy Shifts | Impact |
|----------|-------------|-----------|-------------|-------------------------|--------|

### Sleep Disruption Score (12AM-6AM Pages)
| Engineer | Night Pages (90d) | Avg Per Shift | Sleep Hours Lost (est) | Trend |
|----------|-------------------|---------------|----------------------|-------|

### Shift Quality Analysis
| Shift Window | Avg Pages | Worst Shift Date | Best Shift Date | Notes |
|-------------|-----------|-----------------|-----------------|-------|
| Mon-Fri Day | [N] | [Date: N pages] | [Date: N pages] | |
| Mon-Fri Night | [N] | [Date: N pages] | [Date: N pages] | |
| Weekend Day | [N] | [Date: N pages] | [Date: N pages] | |
| Weekend Night | [N] | [Date: N pages] | [Date: N pages] | |

### Imbalance Root Causes
| Cause | Impact | Engineers Affected | Fix |
|-------|--------|-------------------|-----|
| [e.g., Noisy alarm during specific shifts] | [X extra pages] | [Names] | [Tune alarm / adjust schedule] |

### Burnout Risk Assessment
| Engineer | Risk Level | Factors | Recommended Action |
|----------|-----------|---------|-------------------|
| [Name] | High | [e.g., 3 consecutive heavy shifts, no break in 10 weeks] | [Action] |

### Rotation Adjustment Recommendations
1. [Specific recommendation: e.g., "Swap Alice and Bob's next rotation to even out cumulative load"]
2. [Specific recommendation: e.g., "Add Charlie to secondary rotation to reduce primary burden"]
3. [Specific recommendation: e.g., "Move Dave's shift away from the historically noisy Wednesday window"]

### Month-over-Month Trend
| Engineer | Month 1 Pages/Shift | Month 2 | Month 3 | Trend |
|----------|--------------------|---------|---------| ------|

### Upcoming Rotation Forecast
| Week | Primary | Secondary | Known Issues | Projected Load |
|------|---------|-----------|-------------|----------------|
```

## Delivery
Send the full report as a Slack DM to me every 2 weeks (aligned with rotation changes). Send an immediate alert if any single engineer receives more than 2x the team average pages in a single shift, or if a night page rate exceeds 3 per night for 2 consecutive nights.
