# Infrastructure Drift Detection Report

Detect CDK/CloudFormation drift, manual changes not captured in code, configuration inconsistencies between deployment stages, and infrastructure-as-code compliance. Drift creates operational risk and makes deployments unpredictable.

## Data Sources
- AWS CloudFormation: drift detection results, stack status
- Apollo: deployment configurations, environment variables, host fleet state
- Pipelines: infrastructure deployment history, stage configurations
- Brazil Build System: CDK/IaC package source code
- CRUX CRs: infrastructure code changes
- Oncall system: incidents caused by config drift or manual changes

## Instructions

1. Run drift detection across all team-owned CloudFormation/CDK stacks:
   - Identify resources where actual state differs from template-defined state
   - Categorize drift as: modified properties, deleted resources, or added resources
   - Determine when drift likely occurred (correlate with deployment history)
   - Assess severity: cosmetic drift vs functional drift vs security-relevant drift

2. Compare configurations across stages (dev/beta/gamma/prod):
   - Environment variable differences (expected vs unexpected)
   - Instance types/sizes across stages (dev should be smaller but same family)
   - Security group rules (prod should be strictest)
   - IAM permissions (should not be more permissive in prod than defined in code)
   - Feature flags that differ unexpectedly between stages
   - Timeout values, retry configurations, circuit breaker settings

3. Identify manual changes not in code:
   - Console modifications to resources that should be IaC-managed
   - AWS CLI changes made during incidents that were never codified
   - Apollo configuration overrides that bypass the deployment pipeline
   - Security group rules added manually (common during debugging)
   - Environment variables added directly to hosts/containers

4. Check for infrastructure code quality:
   - Resources without tags (violates tagging policy)
   - Hardcoded values that should be parameters
   - Resources created outside of CDK/CloudFormation (shadow IT)
   - Stacks that haven't been deployed in 90+ days (stale IaC)
   - CDK versions across packages (should be consistent)

5. Review recent infrastructure CRs for:
   - Changes that only went to one stage
   - Rollbacks that were never re-applied
   - Emergency fixes that bypassed normal deployment flow
   - Incomplete deployments (CR merged but pipeline not run)

6. Compliance checks:
   - All resources created via IaC (not console/CLI)
   - All changes go through CR review
   - All stages updated from same source (no stage-specific branches)
   - Encryption at rest enabled for all data stores
   - Logging enabled for all services
   - Backup configurations present for stateful resources

## Output Format

```
## Infrastructure Drift Report
**Scan Date:** [date]
**Team:** [team name]
**Stacks Scanned:** [n]
**Resources with Drift:** [n] / [total resources]
**Stages Compared:** [dev, beta, gamma, prod]

---

### Drift Summary

| Severity | Count | Examples |
|----------|-------|---------|
| Critical (security-relevant) | [n] | [brief description] |
| High (functional difference) | [n] | [brief description] |
| Medium (config inconsistency) | [n] | [brief description] |
| Low (cosmetic/tagging) | [n] | [brief description] |

---

### CloudFormation/CDK Drift

| Stack | Resource | Property | Expected (IaC) | Actual (AWS) | Severity | When Changed |
|-------|----------|----------|----------------|--------------|----------|--------------|
| [stack] | [resource] | [property] | [value] | [value] | [sev] | [estimate] |

---

### Stage Configuration Inconsistencies

| Configuration | Dev | Beta | Gamma | Prod | Expected Pattern | Issue |
|--------------|-----|------|-------|------|-----------------|-------|
| [config item] | [val] | [val] | [val] | [val] | [what it should be] | [what's wrong] |

**Unexpected differences:**
- [detail about configs that should match but don't]
- [detail about prod having settings not present in lower stages]

---

### Manual Changes Detected (Not in Code)

| Resource | Change | Who (if known) | When | Likely Reason | Codified? |
|----------|--------|---------------|------|---------------|-----------|
| [resource] | [what changed] | [person/unknown] | [date] | [incident/debugging/unknown] | [no] |

**Common pattern:** [e.g., "Security group rules added during incident [ID] never put into CDK"]

---

### Shadow Resources (Created Outside IaC)

| Resource | Type | Account/Region | Created | Creator | Purpose |
|----------|------|---------------|---------|---------|---------|
| [ID]     | [type] | [account/region] | [date] | [who] | [known/unknown] |

---

### IaC Code Quality Issues

| Issue | Package | Details | Fix Complexity |
|-------|---------|---------|----------------|
| [issue] | [pkg] | [details] | [Low/Med/High] |

---

### Recent Incomplete Deployments

| CR | Merged | Deployed To | Missing Stages | Status |
|----|--------|-------------|----------------|--------|
| [CR ID] | [date] | [stages] | [stages not deployed] | [stuck/pending/forgotten] |

---

### Remediation Plan

| Priority | Item | Action | Owner | Effort |
|----------|------|--------|-------|--------|
| 1 | [critical drift] | [codify and deploy fix] | [who] | [estimate] |
| 2 | [manual change] | [add to CDK, deploy through pipeline] | [who] | [estimate] |
| 3 | [inconsistency] | [align stages] | [who] | [estimate] |

---

### Recommendations
1. **Immediate:** [fix critical/security-relevant drift]
2. **This sprint:** [codify manual changes, align stages]
3. **Process:** [e.g., "Add post-incident step to codify emergency changes within 48 hours"]
4. **Prevention:** [e.g., "Enable CloudFormation drift detection on schedule"]
5. **Governance:** [e.g., "Restrict console write access to prevent manual changes"]
```

## Delivery
Send the formatted report as a Slack DM to me. If any security-relevant drift is detected (security groups, IAM policies, encryption settings), flag as URGENT at the top and recommend immediate remediation. Run this report bi-weekly.
