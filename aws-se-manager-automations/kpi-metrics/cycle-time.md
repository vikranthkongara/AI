# Cycle Time Metrics

Measure average time from CR creation to merge for each engineer and the team overall, tracking trends and identifying bottlenecks.

## Data Sources
- **CRUX CRs**: All code reviews created and merged in the measurement period
- **Taskei**: Linked tickets to understand work type (feature, bug fix, refactor)
- **Calendar**: Working days calculation (exclude weekends, holidays, PTO)

## Instructions

1. **Pull all merged CRs for the measurement period** (default: last 30 days):
   - CR creation timestamp
   - First review timestamp
   - First approval timestamp
   - Final merge timestamp
   - Number of revision iterations
   - Lines of code changed
   - Author and reviewers

2. **Calculate per-CR cycle time breakdown**:
   - Total cycle time: creation to merge
   - Time to first review: creation to first reviewer comment/approval
   - Review time: first review to final approval
   - Merge delay: final approval to actual merge
   - Rework time: time spent between revision iterations

3. **Aggregate by engineer**:
   - Average cycle time per engineer
   - Median cycle time (to reduce outlier impact)
   - P90 cycle time (worst case)
   - Number of CRs in measurement period
   - Trend vs previous period (improving/declining)

4. **Aggregate by team**:
   - Team average and median cycle time
   - Team P90 cycle time
   - Week-over-week trend
   - Comparison to organizational benchmarks if available

5. **Identify outliers and patterns**:
   - CRs with unusually long cycle times - why? (large CRs, complex reviews, reviewer unavailability)
   - CRs that were merged exceptionally fast - are they appropriately reviewed?
   - Correlation between CR size and cycle time
   - Impact of number of reviewers on cycle time

6. **Break down by work type**:
   - Feature work cycle time vs bug fix cycle time
   - Small CRs (<50 lines) vs medium (50-200) vs large (200+)
   - CRs with external reviewers vs internal only

## Output Format

```
# Cycle Time Report - [Period: Start Date to End Date]

## Team Summary
- Average cycle time: [hours/days]
- Median cycle time: [hours/days]
- P90 cycle time: [hours/days]
- Total CRs merged: [count]
- Trend: [improving/stable/declining] vs previous period ([+/-X%])

## Cycle Time Breakdown (Avg)
| Phase | Duration | % of Total |
|-------|----------|-----------|
| Time to first review | [hours] | [%] |
| Review & iteration | [hours] | [%] |
| Approval to merge | [hours] | [%] |

## Per-Engineer Metrics

| Engineer | CRs Merged | Avg Cycle Time | Median | P90 | Trend |
|----------|-----------|----------------|--------|-----|-------|
| [name] | [count] | [hours] | [hours] | [hours] | [arrow] |

## By CR Size

| Size Category | Avg Cycle Time | Count | Recommendation |
|---------------|---------------|-------|----------------|
| Small (<50 lines) | [hours] | [count] | - |
| Medium (50-200) | [hours] | [count] | - |
| Large (200+) | [hours] | [count] | Consider breaking up |

## Bottleneck Analysis
- Biggest delay phase: [time to first review / review iteration / merge delay]
- CRs stuck longest: [CR-xxx] ([X] days - reason: [waiting on reviewer Y])
- Reviewers contributing to delay: [names with high avg review response time]

## Trends (Last 4 Weeks)
- Week 1: [avg hours] | Week 2: [avg hours] | Week 3: [avg hours] | Week 4: [avg hours]
- Direction: [improving/stable/declining]

## Recommendations
- [If time-to-first-review is bottleneck: suggest review rotation or pairing]
- [If large CRs are slow: encourage smaller, incremental CRs]
- [If specific reviewer is bottleneck: suggest load balancing]
```

## Delivery
- Send as Slack DM to me every Monday morning (weekly report)
- Include month-over-month comparison on the first Monday of each month
- Flag if team average cycle time exceeds 48 hours (threshold for action)
