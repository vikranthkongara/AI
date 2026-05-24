# Deployment Frequency Metrics

Track how often the team deploys to production, broken down by service, with trends and comparisons to DORA benchmarks.

## Data Sources
- **Pipelines**: All pipeline executions that reached production
- **Apollo**: Production deployment records with timestamps
- **CRUX CRs**: CRs included in each deployment for change traceability
- **Taskei**: Linked tickets to understand what was deployed (feature, fix, operational)

## Instructions

1. **Count production deployments** for the measurement period (default: last 30 days):
   - Total deployments to production across all team services
   - Deployments per service
   - Deployments per week (for trend analysis)
   - Deployments per engineer (who initiated)

2. **Categorize deployments**:
   - Feature deployments (new functionality)
   - Bug fix deployments
   - Operational/config deployments
   - Security patch deployments
   - Rollbacks (count separately)

3. **Calculate frequency metrics**:
   - Average deployments per day (team-wide)
   - Average deployments per week per service
   - Days between deployments per service (deploy gap)
   - Longest gap without deployment per service

4. **DORA benchmark comparison**:
   - Elite: Multiple deploys per day
   - High: Between once per day and once per week
   - Medium: Between once per week and once per month
   - Low: Less than once per month
   - Classify each service and the team overall

5. **Identify deployment patterns**:
   - Day-of-week distribution (do we avoid Friday deploys?)
   - Time-of-day patterns
   - Batch deployments vs continuous flow
   - Services with decreasing deployment frequency (concern)

6. **Analyze deployment size**:
   - Average number of CRs per deployment
   - Average lines changed per deployment
   - Correlation between deployment size and failure rate
   - Are we doing many small deploys (good) or few large ones (risky)?

## Output Format

```
# Deployment Frequency Report - [Period: Start Date to End Date]

## Team Summary
- Total prod deployments: [count]
- Avg deployments per day: [X]
- Avg deployments per week: [X]
- DORA classification: [Elite/High/Medium/Low]
- Trend: [increasing/stable/decreasing] vs previous period ([+/-X%])

## Per-Service Breakdown

| Service | Deployments | Avg/Week | Avg Gap (days) | DORA Level | Trend |
|---------|-------------|----------|----------------|-----------|-------|
| [svc] | [count] | [X] | [days] | [level] | [arrow] |

## Deployment Categories

| Category | Count | % of Total |
|----------|-------|-----------|
| Feature | [count] | [%] |
| Bug fix | [count] | [%] |
| Operational | [count] | [%] |
| Security | [count] | [%] |
| Rollback | [count] | [%] |

## Per-Engineer Deployment Activity

| Engineer | Deployments Initiated | Services Deployed | Most Active Service |
|----------|----------------------|-------------------|-------------------|
| [name] | [count] | [count] | [service] |

## Weekly Trend

| Week | Deployments | Change vs Prev | Notable Events |
|------|-------------|---------------|----------------|
| [date range] | [count] | [+/-X] | [context] |

## Deployment Patterns
- Busiest day: [day] (avg [X] deploys)
- Quietest day: [day] (avg [X] deploys)
- Peak deployment hour: [time]
- Avg CRs per deployment: [X]
- Avg lines changed per deployment: [X]

## Services of Concern
- [Service X] has not deployed in [Y] days (last: [date])
- [Service Y] deployment frequency declining ([X]/week -> [Y]/week)

## Recommendations
- [If frequency is low: identify blockers to deploying more often]
- [If batch sizes are large: encourage smaller, more frequent deploys]
- [If specific service rarely deploys: investigate why]
```

## Delivery
- Send as Slack DM to me every Monday morning (weekly summary)
- Include a monthly rollup on the first Monday of each month
- Alert if any service goes 7+ days without a production deployment
