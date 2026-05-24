# Rollback Frequency Tracker

Track deployment rollbacks across team services: frequency, root causes, impact duration, and patterns that indicate systemic issues.

## Data Sources
- Pipelines (deployment history, rollback events, stage gates)
- Apollo (deployment status, rollback triggers, canary results)
- Oncall system (incidents triggered by deployments)
- CRUX CRs (code changes that were rolled back)
- Taskei (post-rollback improvement tasks)

## Instructions
1. Query Pipelines and Apollo for all rollback events in the past 30 days across team-owned services. Collect:
   - Service name
   - Deployment ID and timestamp
   - Rollback trigger (automated vs manual)
   - Time from deployment to rollback
   - Time from rollback initiation to full recovery
   - Deployer name
2. For each rollback, determine the root cause:
   - Check the associated CR in CRUX (what code change was deployed?)
   - Check oncall system for related alarms/incidents
   - Categorize: code bug, config error, dependency issue, capacity issue, test gap, other
3. Calculate rollback metrics:
   - Rollback rate: rollbacks / total deployments (per service and overall)
   - Mean time to detect (deployment to rollback decision)
   - Mean time to rollback (decision to full recovery)
   - Customer impact duration
4. Identify patterns:
   - Services with highest rollback rates
   - Engineers with multiple rollbacks (may need mentoring, not punishment)
   - Day/time patterns (e.g., Friday deployments rolled back more often)
   - Common root cause categories
   - Pipeline stages where issues should have been caught
5. Assess deployment safety mechanisms:
   - Are canary deployments catching issues?
   - Are auto-rollback thresholds working?
   - Are bake times sufficient?
6. Check for cascading impacts:
   - Did the rollback affect downstream services?
   - Were there customer-visible issues during the rollback window?
7. Compare against previous months to identify trends.

## Output Format
```
## Rollback Frequency Report
**Period:** [Month Year]
**Total Deployments:** [N]
**Total Rollbacks:** [N]
**Rollback Rate:** [X]% (Target: <[Y]%)

### Summary
| Metric | This Month | Last Month | 3-Month Avg | Trend |
|--------|-----------|------------|-------------|-------|
| Rollback rate | [X]% | [Y]% | [Z]% | [Arrow] |
| Avg detection time | [X min] | [Y min] | [Z min] | [Arrow] |
| Avg rollback time | [X min] | [Y min] | [Z min] | [Arrow] |
| Avg customer impact | [X min] | [Y min] | [Z min] | [Arrow] |

### Rollback Events Detail
| Date | Service | Deployer | Trigger | Root Cause | Detection Time | Impact Duration |
|------|---------|----------|---------|-----------|----------------|-----------------|

### Rollback Rate by Service
| Service | Deployments | Rollbacks | Rate | Trend | Concern Level |
|---------|-------------|-----------|------|-------|---------------|

### Root Cause Distribution
| Category | Count | % | Top Services Affected |
|----------|-------|---|----------------------|
| Code bug | [N] | [X]% | [Services] |
| Config error | [N] | [X]% | [Services] |
| Dependency issue | [N] | [X]% | [Services] |
| Capacity issue | [N] | [X]% | [Services] |
| Test gap | [N] | [X]% | [Services] |
| Other | [N] | [X]% | [Services] |

### Deployment Safety Assessment
| Service | Canary Enabled | Auto-Rollback | Bake Time | Caught by Canary? |
|---------|---------------|---------------|-----------|------------------|

### Where Issues Should Have Been Caught
| Rollback | Should Have Been Caught At | Gap | Improvement |
|----------|---------------------------|-----|-------------|
| [ID] | Unit tests | Missing test coverage | Add test for [scenario] |
| [ID] | Integration tests | Test environment drift | Update test env config |
| [ID] | Canary | Canary metric not monitored | Add [metric] to canary |

### Engineer Rollback Frequency
| Engineer | Rollbacks | Total Deploys | Rate | Context |
|----------|-----------|---------------|------|---------|
[Note: This is for identifying coaching opportunities, not blame]

### Day/Time Pattern
| Day | Deploys | Rollbacks | Rate | Recommendation |
|-----|---------|-----------|------|----------------|

### Customer Impact Summary
| Rollback | Services Affected | Customer Impact | Duration | Severity |
|----------|-------------------|-----------------|----------|----------|

### Improvement Actions
| Action | Expected Impact | Owner | Task ID | Status |
|--------|----------------|-------|---------|--------|

### Recommendations
1. [Specific process or tooling improvement]
2. [Specific testing gap to address]
3. [Specific deployment safety enhancement]
```

## Delivery
Send the full report as a Slack DM to me on the 1st of each month. Send an immediate alert whenever a rollback occurs on a Sev1/2 alarm trigger or when 3+ rollbacks happen in a single week.
