# Operational Load Metrics

Ratio of operational work (oncall, incidents, toil) vs feature work per engineer, tracking operational burden and identifying toil reduction opportunities.

## Data Sources
- **Oncall System**: Pages, incidents, and time spent on oncall activities
- **Taskei**: Tickets categorized as operational vs feature work
- **CRUX CRs**: CRs tagged as operational fixes vs feature development
- **Calendar**: Time spent in incident bridges, operational meetings
- **Slack**: Time spent in oncall channels and incident response threads

## Instructions

1. **Categorize all work for the measurement period** (default: last 30 days):
   - Feature work: New functionality, enhancements, planned improvements
   - Operational work: Oncall responses, incident handling, alarm tuning
   - Toil: Repetitive manual tasks, maintenance, operational overhead
   - Tech debt: Refactoring, dependency updates, infrastructure improvements
   - Unplanned work: Bug fixes, emergency requests, ad-hoc tasks

2. **Measure operational load per engineer**:
   - Story points spent on operational tickets vs feature tickets
   - Number of oncall pages handled
   - Time spent in incident response (from incident timeline)
   - CRs that are operational fixes vs feature work
   - Calendar time in operational meetings vs feature meetings

3. **Calculate ratios**:
   - Team operational load: (operational + toil points) / total points
   - Per-engineer operational load ratio
   - Oncall burden: pages per rotation, time spent per page
   - Unplanned work ratio: unplanned / total work

4. **Track oncall impact on productivity**:
   - Feature work output during oncall week vs non-oncall week
   - Pages during working hours vs after hours
   - Average time to handle a page (from page to resolution)
   - Recovery time after incidents (time before resuming planned work)

5. **Identify toil patterns**:
   - Repetitive operational tasks that could be automated
   - Manual processes that engineers repeatedly complain about
   - Operational tasks taking disproportionate time
   - Growing operational burden (trend analysis)

6. **Assess fairness of distribution**:
   - Is operational load evenly distributed across team?
   - Are some engineers carrying disproportionate oncall burden?
   - Does seniority correlate with operational load (it shouldn't disproportionately)

## Output Format

```
# Operational Load Report - [Period: Start Date to End Date]

## Team Summary
- Feature work: [X]% of total effort
- Operational work: [X]% of total effort
- Toil: [X]% of total effort
- Tech debt: [X]% of total effort
- Target ratio: 70% feature / 20% ops / 10% toil (or team-defined)
- Status: [Healthy / Ops-heavy / Action needed]

## Trend (Last 4 Months)

| Month | Feature % | Ops % | Toil % | Tech Debt % | Direction |
|-------|-----------|-------|--------|-------------|-----------|
| [month] | [%] | [%] | [%] | [%] | [arrow] |

## Per-Engineer Breakdown

| Engineer | Feature % | Ops % | Toil % | Oncall Pages | Status |
|----------|-----------|-------|--------|-------------|--------|
| [name] | [%] | [%] | [%] | [count] | [OK/High ops load] |

## Oncall Burden Analysis
- Avg pages per rotation: [X]
- Avg time per page: [minutes]
- After-hours pages: [X]% of total
- Oncall week productivity impact: -[X]% feature output
- Most paged service: [name] ([X] pages)

## Top Toil Items (Automation Candidates)

| Task | Frequency | Time/Occurrence | Total Time | Automatable? |
|------|-----------|----------------|-----------|--------------|
| [task] | [X/week] | [hours] | [hours/month] | [Yes/Partial/No] |

## Operational Load Distribution Fairness

| Engineer | Ops Load (Last 3 Months) | Team Avg | Deviation |
|----------|-------------------------|----------|-----------|
| [name] | [hours] | [hours] | [+/-X%] |

## Unplanned Work Impact
- Unplanned work this period: [X]%
- Sources: [incidents X%, support escalations Y%, ad-hoc requests Z%]
- Sprint goal impact: [X] stories descoped due to unplanned work

## Recommendations
1. [Automate [toil item] - estimated savings: X hours/month]
2. [Tune alarms for [service] - reduce noise by X pages/month]
3. [Rebalance oncall - [engineer] has handled X% more pages than team avg]
4. [Invest in [operational improvement] to reduce unplanned work]
5. [Set team target: reduce ops load from X% to Y% by [date]]
```

## Delivery
- Send as Slack DM to me every Monday morning
- Monthly detailed report on first Monday of each month
- Alert if team operational load exceeds 40% in any given week
- Include in quarterly planning prep materials
