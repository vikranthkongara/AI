# Dependency Failure Impact Analysis

Analyze how upstream and downstream service failures affect team-owned services, identify single points of failure, and recommend resilience improvements.

## Data Sources
- Oncall system (incidents involving dependencies, cascading failures)
- Apollo (service dependency graphs, health checks)
- Pipelines (deployment dependencies)
- Taskei (resilience improvement tasks, dependency-related tickets)
- Email/Outlook (partner team incident notifications)

## Instructions
1. Query Apollo and the oncall system for the dependency graph of all team-owned services:
   - Upstream dependencies (services we call)
   - Downstream dependents (services that call us)
   - Shared infrastructure dependencies (databases, caches, queues)
2. Analyze incidents from the past 90 days where a dependency failure impacted team services:
   - Which dependency failed?
   - Which team services were affected?
   - What was the customer impact?
   - How long until our service recovered after the dependency recovered?
   - Did we have fallback mechanisms and did they work?
3. Identify single points of failure:
   - Dependencies with no fallback or redundancy
   - Dependencies where failure causes complete service outage (not graceful degradation)
   - Dependencies with SLAs lower than our own SLA commitments
4. Analyze downstream impact:
   - When our services fail, which downstream services are affected?
   - Are downstream services resilient to our failures (retries, circuit breakers)?
   - Have we received complaints from downstream teams?
5. Assess current resilience mechanisms:
   - Circuit breakers configured and working?
   - Retry policies appropriate (not causing thundering herd)?
   - Timeouts configured correctly?
   - Fallback/cache mechanisms in place?
   - Async vs sync dependencies (can we decouple?)
6. Check email for any notifications from partner teams about planned maintenance, deprecations, or known issues with shared dependencies.
7. Calculate dependency risk scores based on:
   - Frequency of dependency failures
   - Impact severity when dependency fails
   - Current resilience mechanisms in place
   - SLA gap (their SLA vs our needs)

## Output Format
```
## Dependency Failure Impact Analysis
**Date:** [Date]
**Period Analyzed:** Last 90 days
**Services Analyzed:** [N]
**Dependencies Mapped:** [N upstream, N downstream]

### Dependency Incident Summary
| Metric | Count | Trend |
|--------|-------|-------|
| Total dependency-related incidents | [N] | [Arrow] |
| Incidents caused by upstream failures | [N] | [Arrow] |
| Incidents we caused for downstream | [N] | [Arrow] |
| Total customer impact minutes | [N] | [Arrow] |

### Upstream Dependency Risk Matrix
| Dependency | Our Services Affected | Failure Count (90d) | Avg Impact Duration | Fallback Exists | Risk Score |
|-----------|----------------------|--------------------|--------------------|----------------|------------|
| [Dep 1] | [Services] | [N] | [X min] | [Yes/No/Partial] | [High/Med/Low] |

### Single Points of Failure (Critical)
| Dependency | Services Affected | If It Fails | Current Mitigation | Gap |
|-----------|-------------------|-------------|-------------------|-----|
| [Dep] | [Services] | [Impact description] | [None/Partial] | [What's missing] |

### Downstream Impact (When We Fail)
| Our Service | Downstream Dependents | Last Failure Impact | Their Resilience | Our Responsibility |
|-------------|----------------------|--------------------|-----------------|--------------------|

### Resilience Mechanism Audit
| Service | Dependency | Circuit Breaker | Retry Policy | Timeout | Fallback | Cache | Score |
|---------|-----------|-----------------|--------------|---------|----------|-------|-------|
| [Svc] | [Dep] | [Y/N/Config] | [Y/N/Config] | [Y/N/ms] | [Y/N/Desc] | [Y/N/TTL] | [X/5] |

### SLA Gap Analysis
| Dependency | Their SLA | Our SLA Requirement | Gap | Risk |
|-----------|-----------|--------------------|----|------|
[Dependencies whose SLA is lower than what we need]

### Recent Dependency Incidents
| Date | Failed Dependency | Our Services Affected | Impact | Recovery Time | Fallback Worked? |
|------|-------------------|----------------------|--------|---------------|-----------------|

### Cascading Failure Patterns
| Pattern | Frequency | Services in Chain | Total Impact | Prevention |
|---------|-----------|-------------------|--------------|-----------|

### Upcoming Risks
| Dependency | Known Issue/Maintenance | Date | Expected Impact | Our Preparation |
|-----------|------------------------|------|-----------------|-----------------|

### Resilience Improvement Recommendations (Prioritized)
| Priority | Service | Dependency | Improvement | Expected Benefit | Effort |
|----------|---------|-----------|-------------|-----------------|--------|
| 1 | [Svc] | [Dep] | Add circuit breaker | Reduce impact by [X]% | [S/M/L] |
| 2 | [Svc] | [Dep] | Add fallback cache | [X]% requests served during outage | [S/M/L] |

### Architecture Recommendations
- [Suggestions for decoupling, async patterns, or redundancy]
```

## Delivery
Send the full report as a Slack DM to me monthly (1st of each month). Send immediate alerts when a new single point of failure is discovered or when a dependency failure cascades to customer impact exceeding 15 minutes.
