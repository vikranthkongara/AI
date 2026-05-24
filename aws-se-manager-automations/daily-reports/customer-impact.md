# Customer Impact Report

Any customer-facing incidents, ticket escalations from support, SLA breaches, and customer experience degradations for team-owned services.

## Data Sources
- **Oncall System**: Customer-impacting incidents and their severity
- **Taskei**: Escalation tickets from support teams, customer-reported bugs
- **Pipelines/Apollo**: Deployments that may have affected customer experience
- **Slack**: Escalation channels, support team communications
- **Email (Outlook)**: Customer escalation threads, support team notifications

## Instructions

1. **Check for customer-impacting incidents**:
   - Any SEV1/SEV2 incidents affecting customer-facing services in last 24h
   - Duration of customer impact
   - Number of customers affected (if available)
   - Whether impact has been fully resolved or is ongoing

2. **Check support escalations**:
   - Tickets escalated from customer support to engineering
   - Severity and urgency of escalations
   - Customer tier (enterprise, standard) if applicable
   - Time since escalation and current status

3. **Check SLA compliance**:
   - Services approaching or breaching SLA thresholds (availability, latency, error rate)
   - API endpoints with elevated error rates
   - Services with latency above p99 SLA commitments
   - Any SLA credits or notifications triggered

4. **Check for degraded experience**:
   - Services operating in degraded mode (feature flags disabled, fallbacks active)
   - Increased error rates even if below SLA threshold
   - Customer-facing features disabled or limited
   - Performance regressions detected after recent deployments

5. **Review customer feedback signals**:
   - Bug reports from customers in the last 24h
   - Repeated reports of the same issue (pattern detection)
   - Feature requests that relate to current pain points

6. **Correlate with recent changes**:
   - Did any deployment in the last 24h coincide with customer impact?
   - Were there config changes that affected customer experience?
   - External dependency outages affecting our customers

## Output Format

```
# Customer Impact Report - [Date]

## Summary
- Active customer-impacting incidents: [count]
- Support escalations (24h): [count]
- SLA breaches: [count]
- Services in degraded mode: [count]
- Overall customer health: [GREEN/YELLOW/RED]

## Active Incidents Affecting Customers

### [Incident Title] - SEV[X]
- **Status**: [Active/Monitoring/Resolved]
- **Started**: [timestamp] | **Duration**: [hours/minutes]
- **Service**: [service name]
- **Customer Impact**: [description - e.g., "Users unable to complete checkout"]
- **Customers Affected**: [count/estimate/percentage]
- **Current Mitigation**: [what's been done]
- **ETA to Resolution**: [estimate]
- **Owner**: [engineer]

## SLA Status

| Service | SLA Target | Current | Status | Trend |
|---------|-----------|---------|--------|-------|
| [svc] | 99.9% avail | [%] | OK/WARNING/BREACH | [up/down/stable] |
| [svc] | <200ms p99 | [ms] | OK/WARNING/BREACH | [up/down/stable] |

## Support Escalations

| Ticket | Customer | Issue | Escalated | Severity | Assignee | Status |
|--------|----------|-------|-----------|----------|----------|--------|
| [id] | [name/tier] | [summary] | [time] | [sev] | [name] | [status] |

## Degraded Services
- [Service X]: Feature Y disabled via feature flag since [date] - [reason]
- [Service Z]: Operating on fallback cache since [date] - [reason]

## Recent Deployments with Customer Impact Risk
- [Service A] deployed [time] - monitoring for impact (CR-xxx)
- [Service B] deployment correlated with [X]% error rate increase

## Recommended Actions
1. [Prioritize resolution of active incident]
2. [Respond to escalation from [customer] - high priority]
3. [Investigate error rate increase in Service B post-deployment]
4. [Schedule RCA for yesterday's incident]
```

## Delivery
- Send as Slack DM to me daily at 8:00 AM
- If a new customer-impacting incident occurs, send immediate alert with initial details
- If an SLA breach occurs, send immediate notification
- Include a weekly customer health trend every Monday
