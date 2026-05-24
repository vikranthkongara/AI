# Sprint Velocity Metrics

Story points completed per sprint, rolling average, predictability score, and capacity planning data.

## Data Sources
- **Taskei**: Sprint data including story points committed, completed, and carried over
- **Calendar**: Sprint dates, team PTO, holidays affecting capacity
- **Historical Taskei data**: Previous sprints for trend analysis

## Instructions

1. **Pull current and historical sprint data** (last 8 sprints minimum):
   - Sprint name and dates
   - Story points committed at sprint start
   - Story points added mid-sprint
   - Story points completed
   - Story points carried over
   - Story points removed/descoped

2. **Calculate velocity metrics**:
   - Velocity per sprint (points completed)
   - 4-sprint rolling average
   - 8-sprint rolling average (for longer-term trend)
   - Velocity per engineer (normalized by team size)
   - Velocity adjusted for capacity (PTO, holidays)

3. **Calculate predictability**:
   - Commitment reliability: completed / committed ratio per sprint
   - Predictability score: 1 - (standard deviation / mean) over last 4 sprints
   - Sprint-over-sprint variance
   - How often does team complete 80%+ of committed work?

4. **Analyze sprint composition**:
   - Feature work vs bug fixes vs operational vs tech debt per sprint
   - Distribution of story point sizes (are we estimating well?)
   - Carry-over analysis (which types of work carry over most?)

5. **Capacity planning data**:
   - Available capacity next sprint (team size - PTO - oncall)
   - Recommended commitment based on rolling average and capacity
   - Buffer recommendation (typically 80% of average velocity)

6. **Identify trends and anomalies**:
   - Is velocity trending up or down?
   - Sprints significantly above/below average - what caused it?
   - Impact of mid-sprint additions on completion rate
   - Impact of team changes (new hires, departures) on velocity

## Output Format

```
# Sprint Velocity Report - [Current Sprint Name]

## Current Sprint Status
- Sprint: [name] | Day [X] of [Y]
- Committed: [X] points
- Completed so far: [X] points ([%])
- Projected: [X] points (based on current pace)

## Velocity History

| Sprint | Committed | Completed | Carry-Over | Capacity | Reliability |
|--------|-----------|-----------|-----------|----------|-------------|
| [name] | [pts] | [pts] | [pts] | [%] | [%] |

## Rolling Averages
- 4-sprint average: [X] points/sprint
- 8-sprint average: [X] points/sprint
- Trend: [increasing/stable/decreasing] ([+/-X] pts vs 3 months ago)

## Predictability
- Predictability score: [X]% (higher is better, target: >80%)
- Commitment reliability: [X]% (completed/committed)
- Standard deviation: [X] points
- Sprints meeting 80%+ commitment: [X] of last [Y]

## Sprint Composition (Last 4 Sprints Avg)

| Category | Points | % of Total | Trend |
|----------|--------|-----------|-------|
| Feature work | [pts] | [%] | [arrow] |
| Bug fixes | [pts] | [%] | [arrow] |
| Operational/toil | [pts] | [%] | [arrow] |
| Tech debt | [pts] | [%] | [arrow] |
| Other | [pts] | [%] | [arrow] |

## Carry-Over Analysis
- Avg carry-over: [X] points ([%] of committed)
- Most common carry-over reasons: [list]
- Tickets that carried over 2+ sprints: [count] (investigate)

## Capacity Planning - Next Sprint
- Team members available: [X] of [Y]
- PTO: [names and dates]
- Oncall: [name] (reduced capacity)
- Effective capacity: [X]%
- Recommended commitment: [X] points (based on [rolling avg] * [capacity %])
- Stretch target: [X] points

## Per-Engineer Velocity (Last 4 Sprint Avg)

| Engineer | Avg Points/Sprint | Trend | Notes |
|----------|------------------|-------|-------|
| [name] | [pts] | [arrow] | [context if relevant] |

## Recommendations
- [Commit to X points next sprint based on data]
- [Address carry-over pattern: break down large tickets]
- [Operational load increasing - consider dedicated toil sprint]
```

## Delivery
- Send as Slack DM to me at the end of each sprint (sprint review prep)
- Send capacity planning data 1 day before sprint planning
- Alert if current sprint is tracking below 70% completion with <3 days remaining
