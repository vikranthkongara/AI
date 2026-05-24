# Operational Excellence Scorecard

Score the team on operational excellence dimensions: monitoring coverage, alarm response time, runbook completeness, incident frequency, and reliability metrics.

## Data Sources
- Oncall system: Incidents (count, severity, resolution time, repeat rate), page volume, escalations
- Apollo: Service health metrics, deployment success rates, canary metrics
- Pipelines: Deployment frequency, rollback rate, pipeline health
- Taskei: Operational improvement tasks, post-mortem action items tracked
- CRUX CRs: Monitoring additions, alarm configuration changes, runbook updates
- Slack: Operational discussions, incident response coordination quality

## Instructions
1. **Incident Metrics** (last 30 days):
   - Total incidents by severity (Sev1, Sev2, Sev3)
   - Mean time to detect (MTTD)
   - Mean time to respond/acknowledge (MTTR-acknowledge)
   - Mean time to resolve (MTTR-resolve)
   - Repeat incident rate (same root cause as previous incident)
   - Customer-impacting incidents vs. caught-before-impact
   - Compare all metrics to previous 30-day period (trend)
2. **Monitoring & Alarming**:
   - Are all team services covered by health monitors?
   - Alarm signal-to-noise ratio: What % of alarms are actionable vs. noise?
   - Are there services without any alarms?
   - Are alarm thresholds appropriate (not too sensitive, not too lax)?
   - Are dashboards maintained and useful during incidents?
3. **Runbook Completeness**:
   - For each service/alarm, does a runbook exist?
   - When were runbooks last updated?
   - Were runbooks followed during recent incidents?
   - Are runbook steps still accurate (do they match current architecture)?
   - Identify alarms without corresponding runbooks
4. **Deployment Safety**:
   - Deployment frequency (higher = better, if safe)
   - Rollback rate (lower = better)
   - Canary success rate
   - Average deployment duration
   - Are deployment guardrails working? (auto-rollback triggered appropriately)
5. **Post-Mortem & Improvement**:
   - Post-mortem completion rate for qualifying incidents
   - Post-mortem action item completion rate
   - Time from incident to post-mortem document
   - Are action items actually preventing repeat incidents?
6. **Oncall Health**:
   - Page volume per shift (is it sustainable?)
   - Pages during off-hours vs. business hours
   - Oncall rotation fairness (are pages distributed evenly?)
   - Oncall burnout risk (consecutive heavy shifts)
7. **Calculate Overall Score**:
   - Weight each dimension and produce a composite score (0-100)

## Output Format
```
## Operational Excellence Scorecard
### Team: {{TEAM_NAME}}
### Period: Last 30 days
### Overall Score: [X] / 100 ([Excellent >85 / Good 70-85 / Fair 55-70 / Needs Work <55])

### Score Breakdown
| Dimension | Score | Weight | Weighted | Trend |
|-----------|-------|--------|----------|-------|
| Incident management | [X/100] | 25% | [Y] | [Up/Down/Stable] |
| Monitoring coverage | [X/100] | 20% | [Y] | [Up/Down/Stable] |
| Runbook completeness | [X/100] | 15% | [Y] | [Up/Down/Stable] |
| Deployment safety | [X/100] | 20% | [Y] | [Up/Down/Stable] |
| Post-mortem culture | [X/100] | 10% | [Y] | [Up/Down/Stable] |
| Oncall health | [X/100] | 10% | [Y] | [Up/Down/Stable] |
| **TOTAL** | | **100%** | **[X/100]** | |

### Incident Metrics
| Metric | This Period | Last Period | Target | Status |
|--------|------------|------------|--------|--------|
| Total incidents | ... | ... | < [X] | [Met/Missed] |
| Sev1 incidents | ... | ... | 0 | [Met/Missed] |
| Sev2 incidents | ... | ... | < [X] | [Met/Missed] |
| MTTD (minutes) | ... | ... | < [X] | [Met/Missed] |
| MTTR (minutes) | ... | ... | < [X] | [Met/Missed] |
| Repeat incidents | ... | ... | 0 | [Met/Missed] |
| Customer impact events | ... | ... | < [X] | [Met/Missed] |

### Monitoring Coverage
| Service | Monitors | Alarms | Dashboard | Coverage |
|---------|----------|--------|-----------|----------|
| ... | [Yes/Partial/No] | [Count] | [Yes/No] | [Full/Partial/Minimal] |

### Runbook Status
| Service/Alarm | Runbook Exists | Last Updated | Accurate | Used in Incident |
|--------------|---------------|-------------|----------|-----------------|
| ... | [Yes/No] | [Date] | [Yes/Unknown] | [Yes/No/N/A] |

### Deployment Safety
| Metric | Value | Target | Status |
|--------|-------|--------|--------|
| Deployment frequency | [X/week] | > [Y/week] | ... |
| Rollback rate | [X%] | < 5% | ... |
| Canary catch rate | [X%] | > 90% | ... |
| Failed deployments | [count] | 0 | ... |

### Post-Mortem Health
- Qualifying incidents: [count]
- Post-mortems completed: [count] ([%])
- Avg time to post-mortem: [X days]
- Action items created: [count]
- Action items completed: [count] ([%])

### Oncall Health
- Avg pages per shift: [count]
- Off-hours pages: [count] ([%])
- Highest-paged engineer: [anonymized, count]
- Shifts with 0 pages: [count] ([%])

### Top 3 Improvement Areas
1. **[Area]**: Current score [X], gap to target [Y]. Action: [Specific improvement]
2. **[Area]**: Current score [X], gap to target [Y]. Action: [Specific improvement]
3. **[Area]**: Current score [X], gap to target [Y]. Action: [Specific improvement]

### Month-over-Month Trend
| Month | Score | Key Change |
|-------|-------|-----------|
| [3 months ago] | ... | ... |
| [2 months ago] | ... | ... |
| [Last month] | ... | ... |
| **This month** | **...** | **...** |
```

## Delivery
Send as a Slack DM to me on the first Monday of each month. If any critical gap is identified (service with no monitoring, runbook missing for frequently-paging alarm), send an immediate alert.
