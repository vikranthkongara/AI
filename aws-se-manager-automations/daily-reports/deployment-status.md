# Deployment Status Report

Check all pipeline deployments in the last 24 hours, flag failures, and report current deployment health across all team-owned services.

## Data Sources
- **Pipelines**: All pipeline executions in the last 24 hours for team-owned packages
- **Apollo**: Deployment status, host health, and rollback events
- **Oncall System**: Any deployment-related incidents or alarms
- **CRUX CRs**: CRs associated with deployed changes (for traceability)

## Instructions

1. **Enumerate team-owned pipelines**: Query all pipelines associated with the team's packages and services.

2. **For each pipeline, check**:
   - Last execution time and status (succeeded, failed, in-progress, rolled back)
   - Which stage the deployment reached (build, test, beta, gamma, prod)
   - If failed: which stage failed and the failure reason
   - If rolled back: what triggered the rollback (alarm, manual, automated)
   - The CR(s) included in the deployment

3. **Check Apollo deployment health**:
   - Current deployment state for each service (fully deployed, partial, rolling)
   - Any hosts in unhealthy state post-deployment
   - Fleet health percentage for each environment (beta, gamma, prod)

4. **Cross-reference with incidents**:
   - Check if any oncall pages were triggered within 30 minutes of a deployment
   - Identify any deployments that correlate with error rate spikes

5. **Summarize deployment velocity**:
   - Count of successful prod deployments in last 24h
   - Average time from pipeline trigger to prod deployment completion
   - Any pipelines that have been stuck or paused

## Output Format

```
# Deployment Status - [Date]

## Summary
- Total deployments (last 24h): [count]
- Successful: [count] | Failed: [count] | In Progress: [count] | Rolled Back: [count]
- Services fully healthy: [count]/[total]

## Failures & Rollbacks (Action Required)

### [Service Name] - FAILED at [stage]
- **Pipeline**: [pipeline name/ID]
- **Failed at**: [timestamp]
- **Stage**: [gamma/prod]
- **Reason**: [build failure / test failure / alarm triggered]
- **CR**: [CR-12345] by [engineer] - "[CR title]"
- **Action needed**: [Suggested next step]

## Successful Deployments

| Service | CR | Engineer | Deployed At | Duration |
|---------|-----|----------|-------------|----------|
| [name] | CR-xxx | [name] | [time] | [mins] |

## Currently In Progress

- [Service]: Stage [gamma], started [time], ETA [time]

## Pipeline Health Concerns
- [Pipeline X] has not run in 3 days (last CR merged but not deployed)
- [Pipeline Y] gamma stage has been stuck for 6 hours
```

## Delivery
- Send as Slack DM to me every morning by 9:00 AM
- If any pipeline has failed or rolled back, send an immediate alert DM when detected
- Include a link to the pipeline execution for any failed deployments
