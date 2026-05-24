# Operational Readiness Scorecard

Score each team-owned service on operational readiness dimensions: monitoring, alerting, runbooks, rollback capability, capacity headroom, and documentation.

## Data Sources
- Oncall system (alarms configured, incident history, monitoring coverage)
- Apollo (deployment configuration, service health, capacity metrics)
- Pipelines (deployment automation, rollback mechanisms, canary settings)
- Taskei (operational readiness tasks, tech debt tickets)
- CRUX CRs (recent operational improvements)

## Instructions
1. Get a complete inventory of all team-owned services from Apollo/Pipelines.
2. For each service, evaluate the following dimensions (score each 0-5):

**Monitoring (0-5):**
- 0: No monitoring
- 1: Basic health check only
- 2: Key metrics tracked but incomplete
- 3: Good coverage of latency, errors, throughput
- 4: Comprehensive including business metrics
- 5: Full observability with tracing, profiling, anomaly detection

**Alerting (0-5):**
- 0: No alarms
- 1: Basic up/down alarm
- 2: Alarms for key metrics but poor thresholds
- 3: Well-tuned alarms with appropriate severity
- 4: Tiered alerting with escalation paths
- 5: Predictive alerting, anomaly-based, low false positive rate

**Runbooks (0-5):**
- 0: No runbooks
- 1: Outdated or incomplete runbooks
- 2: Basic runbooks exist but gaps
- 3: Runbooks for all critical alarms
- 4: Comprehensive, recently tested, with decision trees
- 5: Automated remediation with runbooks as documentation

**Rollback Capability (0-5):**
- 0: No rollback mechanism
- 1: Manual rollback only, untested
- 2: Rollback exists but takes > 30 minutes
- 3: Automated rollback with < 15 minute recovery
- 4: Canary + auto-rollback with fast detection
- 5: Feature flags, instant rollback, zero-downtime

**Capacity (0-5):**
- 0: At or over capacity
- 1: < 10% headroom
- 2: 10-20% headroom
- 3: 20-50% headroom with scaling plan
- 4: Auto-scaling with proven effectiveness
- 5: Elastic with load testing validated well above peak

**Documentation (0-5):**
- 0: No documentation
- 1: Minimal README only
- 2: Basic architecture docs
- 3: Good service docs, API docs, architecture diagrams
- 4: Comprehensive with onboarding guides
- 5: Living documentation, auto-generated where possible, always current

3. For each dimension, pull supporting evidence:
   - Monitoring: Count of dashboards and metrics from monitoring tools
   - Alerting: Number and quality of alarms from oncall system
   - Runbooks: Existence and freshness from oncall system
   - Rollback: Configuration from Apollo and Pipelines
   - Capacity: Current utilization metrics from Apollo
   - Documentation: Check for wiki pages, README, API docs
4. Calculate overall readiness score per service (weighted average).
5. Identify services with critical gaps (any dimension scoring 0-1).
6. Compare current scores to previous assessment (if available) to show improvement trajectory.
7. Check Taskei for existing improvement tasks and their progress.

## Output Format
```
## Operational Readiness Scorecard
**Date:** [Date]
**Services Assessed:** [N]
**Average Score:** [X]/5.0
**Critical Gaps:** [N] (services with any dimension at 0-1)

### Summary Heatmap
| Service | Monitor | Alert | Runbook | Rollback | Capacity | Docs | Overall | Change |
|---------|---------|-------|---------|----------|----------|------|---------|--------|
| [Svc 1] | [0-5] | [0-5] | [0-5] | [0-5] | [0-5] | [0-5] | [X/5] | [+/-] |
| [Svc 2] | [0-5] | [0-5] | [0-5] | [0-5] | [0-5] | [0-5] | [X/5] | [+/-] |

Color key: 0-1 = Red (Critical), 2-3 = Yellow (Needs Work), 4-5 = Green (Good)

### Services Ranked by Readiness
1. [Service] - [X/5] - [Status: Production Ready / Needs Improvement / At Risk]
2. [Service] - [X/5] - [Status]
[All services ranked]

### Critical Gaps (Score 0-1, Immediate Action Required)
| Service | Dimension | Score | Risk | Recommended Action | Effort |
|---------|-----------|-------|------|-------------------|--------|

### Detailed Service Assessments

#### [Service Name] - Overall: [X/5]
| Dimension | Score | Evidence | Gap | Improvement Action |
|-----------|-------|----------|-----|-------------------|
| Monitoring | [X/5] | [What exists] | [What's missing] | [Action] |
| Alerting | [X/5] | [What exists] | [What's missing] | [Action] |
| Runbooks | [X/5] | [What exists] | [What's missing] | [Action] |
| Rollback | [X/5] | [What exists] | [What's missing] | [Action] |
| Capacity | [X/5] | [Current utilization] | [Headroom concern] | [Action] |
| Documentation | [X/5] | [What exists] | [What's missing] | [Action] |

[Repeat for each service]

### Dimension Averages (Team-Wide)
| Dimension | Average Score | Weakest Service | Strongest Service |
|-----------|--------------|-----------------|-------------------|
| Monitoring | [X/5] | [Service] | [Service] |
| Alerting | [X/5] | [Service] | [Service] |
| Runbooks | [X/5] | [Service] | [Service] |
| Rollback | [X/5] | [Service] | [Service] |
| Capacity | [X/5] | [Service] | [Service] |
| Documentation | [X/5] | [Service] | [Service] |

### Improvement Trajectory (vs Last Assessment)
| Service | Previous Score | Current Score | Change | Key Improvements Made |
|---------|--------------|---------------|--------|----------------------|

### Existing Improvement Tasks (Taskei)
| Task ID | Service | Dimension | Status | Assignee |
|---------|---------|-----------|--------|----------|

### Prioritized Improvement Plan
| Priority | Service | Dimension | Current | Target | Action | Effort | Impact |
|----------|---------|-----------|---------|--------|--------|--------|--------|
| 1 | [Svc] | [Dim] | [X] | [Y] | [Specific action] | [S/M/L] | [High/Med/Low] |

### Recommended Sprint Allocation
Allocate [X]% of sprint capacity to operational readiness:
- [Service]: [Action] - [Effort]
- [Service]: [Action] - [Effort]
```

## Delivery
Send the full scorecard as a Slack DM to me on the 1st of each month. Send an immediate alert if any service's capacity score drops to 0-1 (indicating imminent capacity issues).
