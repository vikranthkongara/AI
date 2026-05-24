# Compliance Status Report

Track security review due dates, privacy assessments, compliance training status, and regulatory requirements for all team members and services. Ensures nothing falls through the cracks and avoids last-minute scrambles for compliance deadlines.

## Data Sources
- Taskei: compliance-tagged tickets, security review tasks, assessment deadlines
- Email (Outlook): compliance reminders, training due notices, audit notifications
- Calendar: compliance review meetings, audit preparation sessions
- Oncall system: security review action items, incident compliance follow-ups
- CRUX CRs: security review approvals, compliance-related code changes
- Pipelines: security scanning results, compliance gates in deployment

## Instructions

1. Gather all compliance requirements and their status:

   **Security Reviews:**
   - Services due for periodic security review (typically annual)
   - New features/services requiring initial security review before launch
   - Security review findings still open (remediation status)
   - Threat model freshness (last updated vs code changes since)
   - Penetration testing schedule and results

2. **Privacy Assessments:**
   - Data handling assessments due or overdue
   - Privacy review requirements for new data collection
   - Data retention policy compliance (are we retaining/deleting per policy?)
   - PII inventory accuracy (new data fields added without privacy review?)
   - Cross-border data transfer assessments

3. **Training Status per Team Member:**
   - Required security training (completion status, due dates)
   - Privacy/data handling training
   - Compliance-specific certifications
   - New hire compliance onboarding checklist status
   - Annual refresher training deadlines

4. **Regulatory Requirements:**
   - SOC2/SOX controls applicable to team services
   - Audit evidence collection status
   - Control attestation deadlines
   - Previous audit findings and remediation status
   - Upcoming audits affecting the team

5. **Operational Compliance:**
   - Encryption requirements met (at rest, in transit)
   - Logging/audit trail completeness
   - Access review completion (quarterly/annual)
   - Credential rotation compliance
   - Backup and disaster recovery testing
   - Incident response plan currency

6. **Pipeline Compliance Gates:**
   - Security scanning enabled in all pipelines
   - Compliance checks passing/failing
   - Waivers in place (justified and not expired)
   - Static analysis results (new findings)

7. Calculate risk posture:
   - Items overdue: immediate risk
   - Items due within 30 days: attention needed
   - Items due within 90 days: plan ahead
   - Items with no clear deadline: investigate

## Output Format

```
## Compliance Status Report
**Report Date:** [date]
**Team:** [team name]
**Overall Status:** [Green/Yellow/Red]
**Overdue Items:** [n]
**Due Within 30 Days:** [n]

---

### Compliance Dashboard

| Category | Total Items | Compliant | Due Soon | Overdue | Status |
|----------|------------|-----------|----------|---------|--------|
| Security Reviews | [n] | [n] | [n] | [n] | [G/Y/R] |
| Privacy Assessments | [n] | [n] | [n] | [n] | [G/Y/R] |
| Training | [n] | [n] | [n] | [n] | [G/Y/R] |
| Regulatory Controls | [n] | [n] | [n] | [n] | [G/Y/R] |
| Operational | [n] | [n] | [n] | [n] | [G/Y/R] |

---

### Overdue Items (Action Required Immediately)

| # | Item | Type | Due Date | Days Overdue | Owner | Impact of Non-Compliance |
|---|------|------|----------|-------------|-------|--------------------------|
| 1 | [item] | [type] | [date] | [n] | [who] | [consequence] |

---

### Due Within 30 Days

| # | Item | Type | Due Date | Days Remaining | Owner | Status |
|---|------|------|----------|---------------|-------|--------|
| 1 | [item] | [type] | [date] | [n] | [who] | [not started/in progress] |

---

### Training Status

| Engineer | Security Training | Privacy Training | Other Required | Overall |
|----------|------------------|-----------------|----------------|---------|
| [name]   | [Complete/Due date] | [Complete/Due date] | [Complete/Due date] | [G/Y/R] |

**Team completion rate:** [%]
**Overdue individuals:** [names - needs immediate follow-up]

---

### Security Review Status

| Service | Last Review | Next Due | Open Findings | Threat Model | Status |
|---------|-----------|----------|---------------|--------------|--------|
| [name]  | [date]    | [date]   | [n]           | [current/stale] | [G/Y/R] |

**Open security findings:**
| # | Service | Finding | Severity | Age (days) | Remediation Status |
|---|---------|---------|----------|-----------|-------------------|
| 1 | [service] | [finding] | [sev] | [n] | [in progress/not started/blocked] |

---

### Audit Readiness

| Audit/Assessment | Date | Preparation Status | Evidence Gaps | Owner |
|-----------------|------|-------------------|---------------|-------|
| [audit name] | [date] | [%] ready | [gaps] | [who] |

---

### Pipeline Compliance

| Pipeline | Security Scan | Compliance Gate | Waivers | Status |
|----------|--------------|-----------------|---------|--------|
| [name]   | [enabled/disabled] | [passing/failing] | [n active] | [G/Y/R] |

---

### Upcoming Deadlines (Next 90 Days)

| Date | Item | Type | Owner | Effort to Complete |
|------|------|------|-------|-------------------|
| [date] | [item] | [type] | [who] | [estimate] |

---

### Recommendations
1. **Immediate:** [address overdue items - specific actions per item]
2. **This week:** [send training reminders to [names]]
3. **This sprint:** [begin security review for [service] due in [n] days]
4. **Process:** [e.g., "Add compliance due dates to sprint planning calendar"]
5. **Prevention:** [e.g., "Set up automated reminders 30 days before deadlines"]
```

## Delivery
Send the formatted report as a Slack DM to me. If any items are overdue or if training completion rate is below 90%, flag URGENT at the top. For overdue training, include a draft reminder message I can send to individual team members. Run this report bi-weekly.
