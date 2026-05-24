# API Health Report

Monitor API latency trends, error rate spikes, deprecated endpoint usage, and upcoming contract changes across team-owned services. This provides early warning of degradation before it impacts customers or triggers pages.

## Data Sources
- CloudWatch/Monitoring: API latency percentiles, error counts, request volumes
- Apollo: service configurations, endpoint definitions
- Pipelines: recent deployments correlating with metric changes
- CRUX CRs: API contract changes, deprecated endpoint annotations
- Oncall system: API-related pages and incidents
- Taskei: API migration tickets, deprecation timelines

## Instructions

1. For each team-owned API service, pull metrics for the past 7 days (with comparison to prior 7 days):
   - Request volume (total and per-endpoint)
   - Latency percentiles: p50, p90, p99, p99.9
   - Error rates: 4xx (client errors), 5xx (server errors)
   - Availability (successful requests / total requests)
   - Throttling/rate limiting events
   - Timeout occurrences

2. Identify latency regressions:
   - Endpoints where p99 increased > 20% week-over-week
   - Endpoints approaching SLA thresholds (e.g., p99 within 80% of SLA limit)
   - Correlate regressions with recent deployments (check Pipelines for deployment timestamps)
   - Identify if regression is consistent or intermittent (specific time of day, specific caller)

3. Analyze error rate patterns:
   - Error rate spikes (when, duration, affected endpoints)
   - New error types appearing (error codes not seen before)
   - Client error patterns suggesting API misuse by callers
   - Server error clusters suggesting systemic issues
   - Error rates by caller (specific clients having issues)

4. Check deprecated endpoint usage:
   - Endpoints marked as deprecated that still receive traffic
   - Which callers are still using deprecated endpoints
   - Deprecation timeline vs actual migration progress
   - Endpoints approaching sunset date with remaining traffic

5. Review upcoming API changes:
   - CRUX CRs with API contract changes (new fields, removed fields, behavior changes)
   - Version bumps planned that may affect callers
   - Breaking changes in our dependencies' APIs
   - New endpoints recently launched (monitoring adequacy check)

6. Traffic pattern analysis:
   - Unusual traffic patterns (sudden drops, unexpected spikes)
   - Traffic growth rate (capacity planning signal)
   - New callers that appeared this week
   - Top callers by volume (concentration risk)

## Output Format

```
## API Health Report
**Period:** Past 7 days (vs prior 7 days)
**Team:** [team name]
**Services Monitored:** [n]
**Overall Availability:** [%] (target: [%])

---

### Service Health Summary

| Service | Availability | p50 Latency | p99 Latency | Error Rate | Traffic | Status |
|---------|-------------|-------------|-------------|------------|---------|--------|
| [name]  | [%]         | [ms]        | [ms]        | [%]        | [req/s] | [Healthy/Degraded/Critical] |

---

### Latency Regressions

| Service | Endpoint | Metric | Last Week | This Week | Change | Likely Cause |
|---------|----------|--------|-----------|-----------|--------|--------------|
| [name]  | [path]   | p99    | [ms]      | [ms]      | [+%]   | [deployment/traffic/dependency] |

**Approaching SLA threshold:**
- [service]/[endpoint]: p99 at [ms], SLA limit is [ms] ([%] of limit consumed)

---

### Error Rate Analysis

| Service | Endpoint | Error Type | Rate | Volume | Trend | Impact |
|---------|----------|-----------|------|--------|-------|--------|
| [name]  | [path]   | [4xx/5xx] | [%]  | [n/day]| [up/down/stable] | [impact] |

**New error patterns:**
- [description of new errors not seen before]

**Top errors by volume:**
1. [error] - [n] occurrences - [likely cause]
2. [error] - [n] occurrences - [likely cause]

---

### Deprecated Endpoint Usage

| Endpoint | Deprecated Since | Sunset Date | Daily Calls | Active Callers | Migration Status |
|----------|-----------------|-------------|-------------|----------------|-----------------|
| [path]   | [date]          | [date]      | [n]         | [list]         | [% migrated]    |

**Action needed:** [callers to contact, migration support needed]

---

### Upcoming API Changes

| Service | Change | Type | CR/Ticket | Target Date | Breaking? | Callers to Notify |
|---------|--------|------|-----------|-------------|-----------|-------------------|
| [name]  | [description] | [add/modify/remove] | [ref] | [date] | [yes/no] | [list] |

---

### Traffic Patterns

| Service | Avg Req/s | Peak Req/s | Growth Rate (WoW) | Capacity Headroom |
|---------|-----------|-----------|-------------------|-------------------|
| [name]  | [n]       | [n]       | [%]               | [%]               |

**Anomalies:**
- [unusual patterns, unexpected traffic sources, etc.]

---

### Correlation with Deployments

| Deployment | Time | Service | Metric Impact | Rollback Needed? |
|-----------|------|---------|---------------|------------------|
| [pipeline run] | [datetime] | [service] | [metric change observed] | [yes/no] |

---

### Recommendations
1. **Immediate:** [address any critical degradation]
2. **This sprint:** [investigate latency regressions, fix error sources]
3. **Communication:** [notify callers about deprecations/changes]
4. **Capacity:** [scale recommendations based on growth trends]
5. **Monitoring:** [gaps in observability to address]
```

## Delivery
Send the formatted report as a Slack DM to me. If any service availability drops below SLA target or p99 latency exceeds SLA, flag as URGENT at the top. For deprecated endpoints approaching sunset with remaining callers, include a draft notification message I can send to those teams.
