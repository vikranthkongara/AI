# Lead Time Metrics

Time from Taskei ticket creation to production deployment, broken down by stages to identify where work gets stuck.

## Data Sources
- **Taskei**: Ticket creation date, status transition timestamps, completion date
- **CRUX CRs**: CR creation and merge timestamps linked to tickets
- **Pipelines**: Deployment timestamps for changes linked to tickets
- **Apollo**: Production deployment confirmation timestamps

## Instructions

1. **Pull all completed tickets** from the measurement period (default: last 30 days):
   - Ticket creation timestamp
   - Each status transition timestamp (To Do -> In Progress -> In Review -> Done)
   - Linked CR creation and merge timestamps
   - Deployment to production timestamp
   - Ticket priority and story points

2. **Calculate total lead time**:
   - End-to-end: ticket creation to production deployment
   - Exclude tickets that are not deployed (docs, process tasks)
   - Per ticket and aggregated (average, median, P90)

3. **Break down into stages**:
   - Queue time: creation to first status change (waiting to be picked up)
   - Development time: In Progress start to CR creation
   - Review time: CR creation to CR merge
   - Deployment time: CR merge to production deployment
   - Identify which stage takes the longest (bottleneck)

4. **Analyze by ticket attributes**:
   - By priority (P1 vs P2 vs P3 - do high priority items move faster?)
   - By size (story points - do large items have proportionally longer lead time?)
   - By type (feature vs bug fix vs operational)
   - By engineer (individual lead time patterns)

5. **Identify outliers and patterns**:
   - Tickets with exceptionally long lead times - which stage caused it?
   - Tickets that moved through quickly - what made them efficient?
   - Recurring bottleneck stages
   - Impact of dependencies on lead time

6. **Calculate flow efficiency**:
   - Active time (actually being worked on) vs wait time (in queues)
   - Flow efficiency = active time / total lead time
   - Where is time being wasted in waiting?

## Output Format

```
# Lead Time Report - [Period: Start Date to End Date]

## Summary
- Avg lead time (creation to prod): [days]
- Median lead time: [days]
- P90 lead time: [days]
- Tickets measured: [count]
- Trend: [improving/stable/worsening] vs previous period
- Flow efficiency: [X]% (active time / total time)

## Stage Breakdown (Averages)

| Stage | Duration | % of Total | Bottleneck? |
|-------|----------|-----------|-------------|
| Queue (waiting to start) | [days] | [%] | [Yes/No] |
| Development | [days] | [%] | [Yes/No] |
| Code Review | [days] | [%] | [Yes/No] |
| Deployment | [days] | [%] | [Yes/No] |
| **Total** | **[days]** | **100%** | - |

## By Priority

| Priority | Avg Lead Time | Median | Count | Meeting SLA? |
|----------|--------------|--------|-------|-------------|
| P1 | [days] | [days] | [count] | [Yes/No - target: <X days] |
| P2 | [days] | [days] | [count] | [Yes/No - target: <X days] |
| P3 | [days] | [days] | [count] | [Yes/No - target: <X days] |

## By Size

| Size (Points) | Avg Lead Time | Median | Count |
|---------------|--------------|--------|-------|
| 1-2 (small) | [days] | [days] | [count] |
| 3-5 (medium) | [days] | [days] | [count] |
| 8+ (large) | [days] | [days] | [count] |

## By Engineer

| Engineer | Avg Lead Time | Median | Tickets | Primary Bottleneck |
|----------|--------------|--------|---------|-------------------|
| [name] | [days] | [days] | [count] | [stage] |

## Weekly Trend

| Week | Avg Lead Time | Median | Tickets Completed |
|------|--------------|--------|-------------------|
| [date] | [days] | [days] | [count] |

## Flow Efficiency Analysis
- Active work time: [X]% of total lead time
- Queue/wait time: [X]% of total lead time
- Biggest wait: [stage] averaging [days] of idle time
- Improvement potential: Reducing [stage] wait by 50% would save [X] days

## Longest Lead Time Items

| Ticket | Title | Lead Time | Bottleneck Stage | Reason |
|--------|-------|-----------|-----------------|--------|
| TASK-xxx | [title] | [days] | [stage] | [reason for delay] |

## Recommendations
1. [Reduce queue time by limiting WIP to X items per engineer]
2. [Speed up review stage with dedicated review slots]
3. [Automate deployment to reduce deploy wait time]
4. [Break down large tickets - 8+ point items take X times longer]
```

## Delivery
- Send as Slack DM to me every Monday morning
- Monthly trend report on first Monday of each month
- Alert if any P1 ticket lead time exceeds SLA threshold
- Include in quarterly planning and process improvement discussions
