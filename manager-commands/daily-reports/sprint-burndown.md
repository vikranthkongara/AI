# Sprint Burndown Report

Current sprint progress showing stories completed vs remaining, velocity trend, and items at risk of not completing by sprint end.

## Data Sources
- **Taskei**: Current sprint board - all tickets, their statuses, story points, and assignments
- **CRUX CRs**: Linked CRs to determine if "In Review" items are close to completion
- **Calendar**: Sprint end date, upcoming holidays or PTO that reduce capacity
- **Historical Taskei data**: Previous sprint velocities for comparison

## Instructions

1. **Pull current sprint details**:
   - Sprint name, start date, end date, days remaining
   - Total story points committed
   - Story points completed (Done status)
   - Story points in progress (In Progress + In Review)
   - Story points not started (To Do)

2. **Calculate burndown metrics**:
   - Ideal burndown line (total points / sprint days)
   - Actual burndown (points completed per day)
   - Current deviation from ideal (ahead/behind by X points)
   - Projected completion based on current velocity

3. **Assess at-risk items**:
   - Tickets "In Progress" with no linked CR (may not be close to done)
   - Tickets "In Progress" for more than half the sprint
   - Tickets with blockers that reduce remaining working time
   - Large-point tickets not yet started with few days remaining

4. **Account for capacity**:
   - Check calendar for team PTO in remaining sprint days
   - Factor in oncall rotation (reduced capacity for oncall engineer)
   - Account for any known meetings or operational work

5. **Compare to velocity trend**:
   - Average velocity over last 4 sprints
   - Is current sprint tracking above or below average?
   - Predictability score (how consistent is velocity sprint-to-sprint)

6. **Identify carryover risk**:
   - Tickets likely to carry over to next sprint
   - Impact of carryover on sprint goals
   - Suggestions for scope adjustment if behind

## Output Format

```
# Sprint Burndown - [Date]
## Sprint: [Sprint Name] | Day [X] of [Y] | [Z] days remaining

## Progress Summary
| Metric | Value | Status |
|--------|-------|--------|
| Total Committed | [X] points | - |
| Completed | [X] points ([%]) | On Track / At Risk / Behind |
| In Progress | [X] points | - |
| Not Started | [X] points | - |
| Ideal Burndown | [X] points by today | - |
| Deviation | [+/-X] points | Ahead / Behind |

## Burndown Trend
- Day 1: [X] remaining | Day 2: [X] remaining | ... | Today: [X] remaining
- Ideal: [X] | Actual: [X] | Gap: [X]

## Projection
- At current velocity: Sprint will complete [X]% of committed work
- To finish on time: Need [X] points/day (current avg: [Y] points/day)
- Confidence: [High/Medium/Low]

## At-Risk Items

| Ticket | Assignee | Points | Status | Risk Reason |
|--------|----------|--------|--------|-------------|
| TASK-xxx | [name] | [pts] | [status] | [reason] |

## Sprint Goals Status
- [ ] [Goal 1] - [On Track / At Risk / Blocked] - [details]
- [ ] [Goal 2] - [On Track / At Risk / Blocked] - [details]
- [ ] [Goal 3] - [On Track / At Risk / Blocked] - [details]

## Capacity Remaining
- Available engineer-days: [X]
- PTO: [names] out [dates]
- Oncall: [name] (reduced capacity)
- Effective capacity: [X]%

## Velocity Comparison
- Current sprint pace: [X] pts/sprint (projected)
- 4-sprint average: [X] pts/sprint
- Predictability: [X]% (std dev / mean)

## Recommended Actions
- [Consider descoping TASK-xxx (low priority, won't finish)]
- [TASK-yyy needs help - reassign or pair]
- [Sprint goal Z at risk - discuss in sprint review]
```

## Delivery
- Send as Slack DM to me daily at 9:00 AM
- On the last 3 days of sprint, send twice daily (morning and 3 PM)
- Flag clearly if sprint goals are at risk of not being met
