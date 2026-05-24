# Mean Time to Recovery (MTTR)

Mean time to recovery for incidents, trend over past 30 days, broken down by severity and service.

## Data Sources
- **Oncall System**: Incident records with start time, detection time, mitigation time, resolution time
- **Apollo**: Rollback timestamps and deployment recovery times
- **Pipelines**: Hotfix deployment durations
- **Taskei**: Incident tickets with timeline details
- **Slack**: Incident channel timestamps for coordination events

## Instructions

1. **Pull all incidents from the measurement period** (default: last 30 days):
   - Incident start time (when issue began)
   - Detection time (when we became aware)
   - Acknowledgment time (when oncall engaged)
   - Mitigation time (when customer impact stopped)
   - Full resolution time (when root cause was fixed permanently)

2. **Calculate MTTR metrics**:
   - Mean Time to Detect (MTTD): incident start to detection
   - Mean Time to Acknowledge (MTTA): detection to acknowledgment
   - Mean Time to Mitigate (MTTM): acknowledgment to mitigation
   - Mean Time to Recover (MTTR): incident start to full mitigation
   - Mean Time to Resolve: incident start to permanent fix deployed

3. **Break down by severity**:
   - SEV1 incidents: MTTR and all sub-metrics
   - SEV2 incidents: MTTR and all sub-metrics
   - SEV3 incidents: MTTR and all sub-metrics

4. **Break down by service**:
   - MTTR per service
   - Which services recover fastest/slowest
   - Trend per service

5. **Break down by recovery method**:
   - Rollback: how fast are rollbacks?
   - Hotfix: how fast can we ship a fix?
   - Configuration change: how fast to toggle?
   - Infrastructure scaling: how fast to scale?

6. **DORA benchmark comparison**:
   - Elite: Less than 1 hour
   - High: Less than 1 day
   - Medium: Less than 1 week
   - Low: More than 1 week

7. **Identify improvement opportunities**:
   - Incidents where detection was slow (monitoring gaps)
   - Incidents where mitigation was slow (runbook gaps or complexity)
   - Incidents that could have been mitigated faster with better tooling
   - Repeat incidents (same root cause, could have been prevented)

## Output Format

```
# MTTR Report - [Period: Start Date to End Date]

## Summary
- Total incidents: [count]
- Mean Time to Recovery: [hours/minutes]
- DORA classification: [Elite/High/Medium/Low]
- Trend: [improving/stable/worsening] vs previous period ([+/-X%])
- Best MTTR: [X minutes] ([incident])
- Worst MTTR: [X hours] ([incident])

## Recovery Metrics Breakdown

| Metric | Average | Median | P90 | Trend |
|--------|---------|--------|-----|-------|
| Time to Detect | [min] | [min] | [min] | [arrow] |
| Time to Acknowledge | [min] | [min] | [min] | [arrow] |
| Time to Mitigate | [min] | [min] | [min] | [arrow] |
| Time to Resolve | [hours] | [hours] | [hours] | [arrow] |

## By Severity

| Severity | Incidents | Avg MTTR | Median | Trend |
|----------|-----------|----------|--------|-------|
| SEV1 | [count] | [time] | [time] | [arrow] |
| SEV2 | [count] | [time] | [time] | [arrow] |
| SEV3 | [count] | [time] | [time] | [arrow] |

## By Service

| Service | Incidents | Avg MTTR | Primary Recovery Method |
|---------|-----------|----------|------------------------|
| [svc] | [count] | [time] | [rollback/hotfix/config] |

## By Recovery Method

| Method | Uses | Avg Duration | Success Rate |
|--------|------|-------------|-------------|
| Rollback | [count] | [min] | [%] |
| Hotfix | [count] | [min] | [%] |
| Config change | [count] | [min] | [%] |
| Scaling | [count] | [min] | [%] |
| Manual intervention | [count] | [min] | [%] |

## Weekly Trend (Last 4 Weeks)
- Week 1: Avg MTTR [time] ([count] incidents)
- Week 2: Avg MTTR [time] ([count] incidents)
- Week 3: Avg MTTR [time] ([count] incidents)
- Week 4: Avg MTTR [time] ([count] incidents)

## Slowest Recoveries This Period

| Incident | Service | MTTR | Bottleneck Phase | Root Cause |
|----------|---------|------|-----------------|-----------|
| [title] | [svc] | [time] | [detection/mitigation] | [brief] |

## Improvement Opportunities
1. [Detection gap: Service X has no alarm for scenario Y]
2. [Runbook gap: Incident Z had no documented recovery steps]
3. [Tooling: Rollback for Service A takes too long - automate]
4. [Prevention: Incident repeated - invest in permanent fix]
```

## Delivery
- Send as Slack DM to me every Monday morning
- Monthly trend report on first Monday of each month
- Alert if any single incident MTTR exceeds 4 hours
