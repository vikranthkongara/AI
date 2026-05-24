# Change Failure Rate

Percentage of deployments that caused incidents or required rollbacks, tracked over time with root cause analysis.

## Data Sources
- **Pipelines**: All production deployments and their outcomes
- **Apollo**: Rollback events, failed deployments, host health post-deploy
- **Oncall System**: Incidents correlated with deployment timestamps
- **Taskei**: Post-incident tickets and RCA outcomes

## Instructions

1. **Identify all production deployments** in the measurement period (default: last 30 days):
   - Total count of production deployments
   - Timestamp of each deployment completion

2. **Identify failed changes** (deployments that caused issues):
   - Deployments that were explicitly rolled back
   - Deployments that triggered oncall pages within 30 minutes
   - Deployments that caused error rate spikes above threshold
   - Deployments that required hotfix deployments within 24 hours
   - Deployments that caused customer-impacting incidents

3. **Calculate change failure rate**:
   - Overall: (failed deployments / total deployments) * 100
   - Per service
   - Per engineer (who authored the change)
   - Per deployment category (feature vs fix vs operational)
   - Trend over last 4 weeks

4. **DORA benchmark comparison**:
   - Elite: 0-15%
   - High: 16-30%
   - Medium: 31-45%
   - Low: 46-60%+
   - Classify team and each service

5. **Root cause analysis of failures**:
   - Categorize failure reasons:
     - Insufficient testing (unit/integration/load)
     - Configuration error
     - Dependency incompatibility
     - Race condition / timing issue
     - Insufficient canary coverage
     - Missing feature flag / gradual rollout
   - Identify patterns (same root cause recurring)

6. **Correlate with deployment practices**:
   - CR size of failed deployments vs successful ones
   - Review depth of failed changes (rubber-stamped?)
   - Test coverage of failed changes
   - Whether canary/gamma caught the issue or it escaped to prod

## Output Format

```
# Change Failure Rate - [Period: Start Date to End Date]

## Summary
- Total production deployments: [count]
- Failed deployments: [count]
- Change failure rate: [X]%
- DORA classification: [Elite/High/Medium/Low]
- Trend: [improving/stable/worsening] vs previous period

## Monthly Trend

| Month | Deployments | Failures | Rate | Change |
|-------|-------------|----------|------|--------|
| [month] | [count] | [count] | [%] | [+/-] |

## Per-Service Failure Rate

| Service | Deployments | Failures | Rate | DORA Level |
|---------|-------------|----------|------|-----------|
| [svc] | [count] | [count] | [%] | [level] |

## Failed Deployments Detail

### [Date] - [Service Name]
- **Change**: CR-xxx - "[title]" by [engineer]
- **Failure type**: [Rollback/Incident/Hotfix required]
- **Detection**: [Alarm/Customer report/Manual observation]
- **Time to detect**: [minutes]
- **Impact**: [description]
- **Root cause**: [category - brief explanation]
- **Prevention**: [What could have caught this earlier]

## Root Cause Distribution

| Category | Count | % of Failures | Trend |
|----------|-------|--------------|-------|
| Insufficient testing | [count] | [%] | [arrow] |
| Configuration error | [count] | [%] | [arrow] |
| Dependency issue | [count] | [%] | [arrow] |
| Race condition | [count] | [%] | [arrow] |
| Insufficient canary | [count] | [%] | [arrow] |
| Other | [count] | [%] | [arrow] |

## Correlations
- Avg CR size for failed deploys: [X] lines vs [Y] lines for successful
- Failed deploys with <2 reviewers: [X]%
- Failed deploys without integration tests: [X]%
- Failed deploys that skipped gamma: [X]%

## Recommendations
1. [Top recommendation based on root cause patterns]
2. [Process improvement to catch failures earlier]
3. [Specific service needing attention]
4. [Testing or review practice to improve]
```

## Delivery
- Send as Slack DM to me every Monday morning (weekly update)
- Monthly detailed report on first Monday of each month
- Immediate alert if change failure rate exceeds 30% in a rolling 7-day window
