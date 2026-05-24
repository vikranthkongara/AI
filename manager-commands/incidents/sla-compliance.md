# SLA Compliance Report

Monitor SLA performance across all team-owned services, identifying breaches, near-misses, and trending violations before they become critical.

## Data Sources
- Oncall system (service metrics, availability data, response times)
- Pipelines (deployment impact on SLA metrics)
- Apollo (service health dashboards)
- Email/Outlook (SLA breach notifications, customer complaints)
- Taskei (SLA-related improvement tickets)

## Instructions
1. Query the oncall system and service monitoring for SLA metrics across all team-owned services:
   - Availability (uptime percentage)
   - Latency (p50, p95, p99 against SLA thresholds)
   - Error rates (against SLA thresholds)
   - Throughput capacity
2. For each service, calculate:
   - Current SLA compliance percentage for the billing/reporting period
   - Remaining error budget (how much downtime/degradation is allowed before breach)
   - Burn rate (are we consuming error budget faster than expected?)
3. Identify SLA breaches:
   - Services that have already breached their SLA this period
   - Duration and severity of breach
   - Customer impact and any remediation credits owed
4. Identify near-misses:
   - Services within 10% of breaching SLA
   - Services with accelerating error budget consumption
   - Services that recovered from a breach but are still at risk
5. Analyze trending violations:
   - Services showing consistent degradation over the past 4 weeks
   - Latency creep that hasn't breached SLA yet but is approaching
   - Intermittent availability dips that are becoming more frequent
6. Correlate with deployments from Pipelines:
   - Did any deployment cause SLA degradation?
   - Are there pending deployments that may affect at-risk services?
7. Check email for any external SLA-related communications (customer escalations, partner concerns).
8. Check Taskei for SLA improvement tasks and their progress.

## Output Format
```
## SLA Compliance Report
**Period:** [Start Date] - [Current Date]
**Days Remaining in Period:** [N]
**Services Monitored:** [N]

### Summary
| Status | Count | Services |
|--------|-------|----------|
| Compliant (Green) | [N] | [List] |
| At Risk (Yellow) | [N] | [List] |
| Breached (Red) | [N] | [List] |

### Service Detail

#### [Service Name]
| SLA Metric | Target | Current | Status | Error Budget Remaining |
|-----------|--------|---------|--------|----------------------|
| Availability | [X]% | [Y]% | [G/Y/R] | [Z hours] |
| Latency p99 | [X]ms | [Y]ms | [G/Y/R] | [buffer]ms |
| Error Rate | <[X]% | [Y]% | [G/Y/R] | [Z]% |

[Repeat for each service]

### SLA Breaches This Period
| Service | Metric | SLA Target | Actual | Duration | Customer Impact | Remediation |
|---------|--------|-----------|--------|----------|-----------------|-------------|

### Near-Miss Alerts (Within 10% of Breach)
| Service | Metric | Current | Threshold | Burn Rate | Days Until Breach (projected) |
|---------|--------|---------|-----------|-----------|------------------------------|

### Trending Concerns (4-Week View)
| Service | Metric | Week 1 | Week 2 | Week 3 | Week 4 | Trend | Projected Breach Date |
|---------|--------|--------|--------|--------|--------|-------|----------------------|

### Error Budget Status
| Service | Total Budget | Consumed | Remaining | Burn Rate | Sustainable? |
|---------|-------------|----------|-----------|-----------|--------------|

### Deployment Impact on SLA
| Deployment | Service | Date | SLA Impact | Recovery Time |
|-----------|---------|------|-----------|---------------|

### Active Improvement Efforts
| Service | Task ID | Description | Status | Expected SLA Improvement |
|---------|---------|-------------|--------|-------------------------|

### Recommended Actions
1. [Urgent action for breached services]
2. [Preventive action for at-risk services]
3. [Long-term improvement for trending concerns]
```

## Delivery
Send the full report as a Slack DM to me every Monday morning. Send immediate alerts when any service breaches its SLA or when error budget consumption exceeds 2x the expected daily rate.
