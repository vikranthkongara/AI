# Dependency Risk Report

Identify external team dependencies blocking our work, packages with pending version bumps, third-party service deprecations, and upstream changes that could affect our services. This helps proactively manage risks before they become blockers.

## Data Sources
- Taskei: blocked tickets, dependency-tagged tasks, cross-team requests
- Brazil Build System: package dependency graphs, version pinning, deprecated package warnings
- CRUX CRs: pending CRs from other teams that we depend on
- Pipelines: deployment dependencies, pipeline stage blockers
- Slack: cross-team channels for deprecation announcements
- Email (Outlook): deprecation notices, migration deadlines, API sunset announcements

## Instructions

1. Query Taskei for all tickets currently in "Blocked" status or tagged with "dependency", "waiting-on", or "external-team":
   - Identify the blocking team and contact person
   - Calculate how long each item has been blocked
   - Determine business impact (what feature/milestone is delayed)
   - Check if there's an escalation path or alternate approach

2. Scan Brazil package dependencies for the team's owned packages:
   - Packages with available version bumps not yet adopted (especially security patches)
   - Packages marked as deprecated that we still consume
   - Packages with upcoming end-of-support dates
   - Transitive dependencies with known vulnerabilities
   - Version pins that are more than 2 major versions behind

3. Check CRUX CRs for:
   - Our CRs that are blocked waiting on another team's review
   - Other teams' CRs that will break our interfaces when merged
   - Pending API contract changes in services we consume

4. Review Pipelines for:
   - Deployment stages blocked by external approvals
   - Integration test failures caused by upstream service changes
   - Shared pipeline resources with contention

5. Scan email and Slack for:
   - Service deprecation announcements affecting our dependencies
   - Migration deadlines (with dates and impact)
   - API version sunset notices
   - Infrastructure changes (region migrations, endpoint changes)

6. Risk-score each dependency:
   - **Critical:** Blocking active sprint work, deadline within 2 weeks
   - **High:** Will block soon (2-4 weeks), no mitigation in place
   - **Medium:** Known risk, mitigation possible, deadline 1-3 months out
   - **Low:** Tracking item, no immediate impact

## Output Format

```
## Dependency Risk Report
**Generated:** [date]
**Team:** [team name]
**Active Blockers:** [n]
**Upcoming Risks:** [n]

---

### Critical Blockers (Action Required This Week)

| # | Dependency | Blocking Team | Blocked Since | Impact | Our Tickets Affected |
|---|-----------|---------------|---------------|--------|---------------------|
| 1 | [description] | [team] | [date] ([n] days) | [what's delayed] | [ticket IDs] |

**Escalation Status:** [already escalated / needs escalation / alternative available]

---

### High Priority Risks (2-4 Weeks)

| # | Risk | Source | Deadline | Mitigation Status |
|---|------|--------|----------|-------------------|
| 1 | [e.g., "API v2 sunset"] | [team/service] | [date] | [planned/not started/in progress] |

---

### Package Version Risks

| Package | Current Version | Latest | Behind By | Risk Type | Action Needed |
|---------|----------------|--------|-----------|-----------|---------------|
| [name]  | [ver]          | [ver]  | [n versions] | [security/deprecation/EOL] | [bump/migrate/replace] |

**Deprecated packages still in use:** [n]
**Security patches pending:** [n]

---

### Upcoming Migrations/Deadlines

| Item | Deadline | Effort Estimate | Owner | Status |
|------|----------|-----------------|-------|--------|
| [migration/sunset] | [date] | [days/weeks] | [assigned?] | [not started/in progress/complete] |

---

### Recommended Actions
1. **Escalate:** [specific blocker to escalate, suggest who to contact]
2. **Assign:** [migration work to specific engineers based on expertise]
3. **Plan:** [upcoming risks to add to sprint planning]
4. **Communicate:** [stakeholders to inform about delays]

### Dependencies Map
- We depend on: [list teams and what we need from them]
- Depends on us: [list teams waiting on us - reciprocal awareness]
```

## Delivery
Send the formatted report as a Slack DM to me. If any critical blocker has been stuck for more than 5 business days, include a suggested escalation message I can forward to the blocking team's manager.
