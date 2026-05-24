# Security Findings Report

New security scan findings, SAS risks, overdue remediation items, and security posture updates for team-owned services.

## Data Sources
- **SAS (Security Assessment System)**: Active campaigns, risks, and remediation deadlines
- **Brazil Build System**: Dependency vulnerability scans
- **Pipelines**: Security gate results in deployment pipelines
- **Taskei**: Security remediation tickets and their status
- **Oncall System**: Security-related incidents or alerts

## Instructions

1. **Check SAS for new findings**:
   - Query active SAS campaigns targeting team-owned services
   - New risks identified in the last 24 hours
   - Risk severity (Critical, High, Medium, Low)
   - Remediation deadlines and days remaining
   - Whether risks have been acknowledged and assigned

2. **Check for overdue remediations**:
   - SAS risks past their remediation due date
   - How many days overdue
   - Assigned owner and current status
   - Escalation risk (approaching management escalation threshold)

3. **Dependency vulnerability scan results**:
   - New CVEs affecting team packages
   - Severity of vulnerabilities (CVSS score)
   - Whether patches are available
   - Which packages are affected

4. **Pipeline security gate results**:
   - Any deployments blocked by security gates
   - Security scan failures in the last 24 hours
   - Findings that need to be addressed before deployment can proceed

5. **Security-related tickets**:
   - Taskei tickets tagged with security that are open
   - Progress on security remediations
   - Any security tickets at risk of missing deadlines

6. **Access and permissions review**:
   - Any recent access grants to production systems
   - Unusual permission escalation requests
   - Service roles with overly broad permissions flagged by scans

## Output Format

```
# Security Findings Report - [Date]

## Summary
- New findings (24h): [count]
- Critical/High severity: [count]
- Overdue remediations: [count]
- Days to nearest deadline: [X]
- Active SAS campaigns: [count]

## New Findings (Last 24h)

### [Finding Title] - [CRITICAL/HIGH/MEDIUM]
- **Source**: [SAS/Dependency Scan/Pipeline Gate]
- **Service**: [affected service]
- **Description**: [brief description]
- **Remediation deadline**: [date] ([X] days remaining)
- **Assigned to**: [engineer/Unassigned]
- **Recommended action**: [brief recommendation]

## Overdue Remediations (ACTION REQUIRED)

| Finding | Service | Severity | Due Date | Days Overdue | Owner | Status |
|---------|---------|----------|----------|--------------|-------|--------|
| [title] | [svc] | [sev] | [date] | [days] | [name] | [status] |

## Approaching Deadlines (Next 7 Days)

| Finding | Service | Severity | Due Date | Days Left | Owner | Status |
|---------|---------|----------|----------|-----------|-------|--------|
| [title] | [svc] | [sev] | [date] | [days] | [name] | [status] |

## Dependency Vulnerabilities

| Package | CVE | CVSS | Severity | Patch Available | Status |
|---------|-----|------|----------|----------------|--------|
| [pkg] | [CVE-xxx] | [score] | [sev] | Yes/No | [status] |

## SAS Campaign Status

| Campaign | Risk Count | Remediated | Remaining | Deadline |
|----------|-----------|------------|-----------|----------|
| [name] | [count] | [count] | [count] | [date] |

## Pipeline Security Gates
- [Service X] deployment blocked by [finding] - needs [action]
- [Service Y] passed all security gates

## Recommended Actions
1. [Most urgent action - overdue critical finding]
2. [Assign unassigned findings to engineers]
3. [Update dependency X to patch CVE-xxx]
4. [Schedule time to address approaching deadline items]
```

## Delivery
- Send as Slack DM to me daily at 9:00 AM
- If a new Critical severity finding is detected, send immediate alert
- On Mondays, include a weekly trend of open findings count
- Flag any finding within 3 days of escalation to senior leadership
