# Permission Audit Report

Review team IAM roles, service accounts, and access patterns for least-privilege compliance. Identify over-permissioned roles, unused access, and potential security risks before they become audit findings.

## Data Sources
- AWS IAM: role policies, permission boundaries, access advisor data
- Apollo: service account configurations, deployment roles
- Oncall system: emergency access grants, break-glass usage
- Taskei: access request tickets, permission change requests
- CRUX CRs: IAM policy changes, CDK/CloudFormation permission modifications
- Email (Outlook): access review notifications, compliance deadlines

## Instructions

1. Enumerate all IAM roles and service accounts owned by the team:
   - Service execution roles (what our services run as)
   - Deployment roles (what Pipelines/Apollo uses to deploy)
   - Developer roles (what team members assume for debugging/operations)
   - Cross-account roles (roles in other accounts we own or use)
   - Service accounts (machine identities, API keys)

2. For each role, analyze permissions:
   - List attached policies (managed and inline)
   - Identify wildcard permissions (Resource: "*" or Action: "*")
   - Flag admin-level policies (AdministratorAccess, PowerUserAccess)
   - Check for overly broad service permissions (e.g., s3:* instead of specific actions)
   - Identify permissions not used in past 90 days (via Access Advisor)
   - Check permission boundaries are applied where appropriate

3. Review access patterns:
   - Last time each role was assumed (unused roles are risk)
   - Access patterns vs granted permissions (using more than needed? or much less?)
   - Break-glass/emergency access usage in past quarter
   - Temporary access grants that were never revoked

4. Check for common anti-patterns:
   - Services with access to resources they don't need
   - Production access from development environments
   - Roles that can modify their own permissions
   - Missing MFA requirements on sensitive operations
   - Shared credentials or roles between services that should be separate
   - Hardcoded credentials in code or config (check recent CRs)

5. Review recent permission changes:
   - CRUX CRs modifying IAM policies in past 30 days
   - Whether changes followed principle of least privilege
   - Whether changes had security review

6. Compliance status:
   - Last access review completion date
   - Upcoming access review deadlines
   - Open security findings related to permissions
   - Rotation schedule for credentials/keys

## Output Format

```
## Permission Audit Report
**Audit Date:** [date]
**Team:** [team name]
**Total Roles Reviewed:** [n]
**Findings:** [n critical] | [n high] | [n medium] | [n low]

---

### Critical Findings (Fix Immediately)

| # | Role/Account | Finding | Risk | Remediation |
|---|-------------|---------|------|-------------|
| 1 | [role ARN]  | [e.g., "Admin access on production service role"] | [impact] | [specific fix] |

---

### Role Inventory

| Role | Type | Account | Policies | Wildcard Actions | Last Used | Status |
|------|------|---------|----------|-----------------|-----------|--------|
| [name] | [service/deploy/human] | [account] | [n] | [n] | [date] | [active/unused/over-permissioned] |

---

### Over-Permissioned Roles

| Role | Granted Permissions | Actually Used | Unused Permissions | Recommendation |
|------|--------------------:|:--------------|-------------------|----------------|
| [role] | [n actions] | [n actions] | [n actions] | [scope down to X] |

---

### Unused Access (Candidates for Removal)

| Role/Account | Last Activity | Age | Recommendation |
|-------------|--------------|-----|----------------|
| [name]      | [date or "Never"] | [days] | [remove/investigate/archive] |

---

### Recent Permission Changes

| Date | CR | Author | Change | Least Privilege? | Security Reviewed? |
|------|-----|--------|--------|-----------------|-------------------|
| [date] | [CR ID] | [name] | [summary] | [yes/no/concern] | [yes/no] |

---

### Anti-Patterns Detected

- [ ] **[pattern]:** [details and affected resources]
- [ ] **[pattern]:** [details and affected resources]

---

### Compliance Status

| Requirement | Due Date | Status | Owner |
|------------|----------|--------|-------|
| Quarterly access review | [date] | [complete/overdue/upcoming] | [name] |
| Credential rotation | [date] | [complete/overdue/upcoming] | [name] |
| Security review | [date] | [complete/overdue/upcoming] | [name] |

---

### Action Items

| Priority | Action | Role/Resource | Owner | Due Date |
|----------|--------|---------------|-------|----------|
| Critical | [action] | [target] | [who] | [ASAP/date] |
| High | [action] | [target] | [who] | [date] |
| Medium | [action] | [target] | [who] | [date] |

---

### Recommendations
1. [e.g., "Scope down [role] to remove s3:* - only needs s3:GetObject on [bucket]"]
2. [e.g., "Remove [unused role] - not assumed in 180 days"]
3. [e.g., "Add permission boundary to [role] to prevent privilege escalation"]
4. [e.g., "Schedule access review for [date] - currently overdue"]
```

## Delivery
Send the formatted report as a Slack DM to me. If any critical findings involve production access or potential data exposure, flag URGENT at the top and recommend immediate remediation steps. Do NOT include actual policy documents or credential details in the Slack message - only reference role names and findings.
