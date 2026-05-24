# Availability Metrics

Service uptime, error rates, latency p50/p99 trends for team-owned services, with SLA tracking and degradation alerts.

## Data Sources
- **Apollo**: Service health dashboards, host health, deployment state
- **Oncall System**: Availability-related alarms and incidents
- **Pipelines**: Deployment events that may affect availability
- **Taskei**: SLA-related tickets and remediation work

## Instructions

1. **Pull availability data for all team-owned services** (default: last 30 days):
   - Uptime percentage per service (monthly, weekly, daily)
   - Error rate (5xx responses / total requests)
   - Latency: p50, p90, p95, p99 values
   - Request volume (to contextualize error counts)
   - Availability by endpoint/API (if granular data available)

2. **Track against SLA commitments**:
   - Current availability vs SLA target per service
   - Error budget remaining (how much downtime can we still have this month?)
   - Error budget burn rate (are we consuming budget too fast?)
   - Days until error budget exhaustion at current rate

3. **Identify degradation patterns**:
   - Latency trending upward (even if within SLA)
   - Error rate slowly increasing
   - Availability dips correlated with specific times or events
   - Services approaching SLA thresholds without breaching yet

4. **Correlate with changes**:
   - Availability changes after deployments
   - Latency changes after dependency updates
   - Error rate changes during traffic spikes
   - Seasonal patterns (time of day, day of week)

5. **Break down by failure mode**:
   - Timeout errors vs server errors vs dependency errors
   - Client errors (4xx) trending (may indicate API confusion)
   - Throttling events
   - Circuit breaker activations

6. **Compare across services**:
   - Which service is healthiest vs least healthy?
   - Services trending in wrong direction
   - New services that haven't established baseline yet

## Output Format

```
# Availability Metrics - [Period: Start Date to End Date]

## Summary
- Services monitored: [count]
- All services meeting SLA: [Yes/No]
- Services at risk: [count]
- Overall team availability: [X]%
- Overall error rate: [X]%

## Per-Service Health

| Service | Availability | SLA Target | Error Rate | p50 Latency | p99 Latency | Status |
|---------|-------------|-----------|-----------|-------------|-------------|--------|
| [svc] | [%] | [%] | [%] | [ms] | [ms] | [GREEN/YELLOW/RED] |

## SLA & Error Budget

| Service | SLA | Current | Budget Used | Budget Remaining | Burn Rate | Days to Exhaust |
|---------|-----|---------|-------------|-----------------|-----------|-----------------|
| [svc] | [%] | [%] | [%] | [minutes] | [min/day] | [days] |

## Latency Trends (Last 4 Weeks)

| Service | p50 (now/4w ago) | p99 (now/4w ago) | Direction | Concern? |
|---------|-----------------|-----------------|-----------|----------|
| [svc] | [ms]/[ms] | [ms]/[ms] | [arrow] | [Yes/No] |

## Error Rate Trends (Last 4 Weeks)

| Service | Current | 4w Ago | Direction | Top Error Type |
|---------|---------|--------|-----------|---------------|
| [svc] | [%] | [%] | [arrow] | [timeout/5xx/dependency] |

## Availability Incidents This Period

| Date | Service | Duration | Impact | Root Cause |
|------|---------|----------|--------|-----------|
| [date] | [svc] | [min] | [description] | [cause] |

## Degradation Alerts (Not Yet SLA Breach But Trending)
- [Service X] p99 latency increased 30% over 2 weeks - investigate
- [Service Y] error rate climbing: 0.1% -> 0.3% over 7 days
- [Service Z] availability at 99.92% with SLA of 99.9% - very thin margin

## Traffic & Capacity

| Service | Avg RPS | Peak RPS | Capacity Headroom | Growth Rate |
|---------|---------|----------|-------------------|-------------|
| [svc] | [rps] | [rps] | [X]% | [X]%/month |

## Recommendations
1. [Service X needs capacity review - headroom below 20%]
2. [Service Y latency regression - correlates with deployment on [date]]
3. [Service Z error budget nearly exhausted - freeze non-critical deploys]
4. [Add latency alarm for Service W - no p99 alarm configured]
5. [Schedule load test for Service V - traffic growing faster than capacity]
```

## Delivery
- Send as Slack DM to me every Monday morning (weekly summary)
- Daily snapshot if any service is in YELLOW or RED status
- Immediate alert if any service breaches SLA
- Monthly report with 30-day trends on first Monday of each month
