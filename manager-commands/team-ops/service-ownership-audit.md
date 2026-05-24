# Service Ownership Audit

Verify all team-owned services have proper operational readiness: updated runbooks, active oncall rotation, monitoring dashboards, documented SLAs, and clear ownership. This prevents operational blind spots and ensures we meet Amazon's operational excellence bar.

## Data Sources
- Apollo: service deployments, host fleets, environment configurations
- Oncall system: rotation assignments, coverage gaps, escalation paths
- Pipelines: deployment pipelines per service, pipeline health
- Taskei: operational readiness tickets, service health tasks
- CRUX CRs: recent changes to each service (indicates active development)
- Brazil Build System: package ownership metadata

## Instructions

1. Enumerate all services owned by the team:
   - Query Apollo for all services/applications deployed by team members
   - Cross-reference with Brazil package ownership
   - Include services in development (pre-production) that will need ops readiness
   - Note any services that may have unclear ownership (shared with other teams)

2. For each service, audit the following operational readiness criteria:

   **Oncall Coverage:**
   - Is there an active oncall rotation assigned?
   - Is the rotation staffed (no gaps in schedule)?
   - Are there at least 2 trained oncallers?
   - Is there a secondary/escalation path defined?

   **Runbooks:**
   - Does a runbook exist?
   - When was it last updated? (Stale if > 90 days without update and service has changed)
   - Does it cover: common alerts, troubleshooting steps, rollback procedures, escalation contacts?
   - Are runbook links accessible from monitoring dashboards?

   **Monitoring & Alerting:**
   - Are there dashboards configured? (CloudWatch, internal monitoring)
   - Key metrics monitored: latency, error rate, throughput, saturation
   - Are alerts configured for SLA breaches?
   - Is there a canary/synthetic monitoring?
   - When were alert thresholds last reviewed?

   **SLA/SLO Documentation:**
   - Are SLAs documented? (availability target, latency targets)
   - Are SLOs defined and measured?
   - Is there an error budget policy?
   - Are SLA commitments communicated to dependent teams?

   **Deployment Readiness:**
   - Is there an automated deployment pipeline?
   - Is rollback tested and documented?
   - Are there deployment guardrails (alarms, bake time)?
   - Last successful deployment date (stale services are risky)

   **Security & Compliance:**
   - Last security review date
   - Are credentials rotated on schedule?
   - Is the service using approved authentication mechanisms?
   - Any open security findings?

3. Score each service on a readiness scale:
   - **Green (Fully Ready):** All criteria met, recently validated
   - **Yellow (Gaps):** Most criteria met, 1-2 minor gaps
   - **Red (At Risk):** Multiple missing criteria, operational risk

4. Identify patterns across services:
   - Common gaps (e.g., all services missing canary monitoring)
   - Services with recent code changes but stale runbooks
   - Single points of failure (only one person knows a service)

## Output Format

```
## Service Ownership Audit
**Audit Date:** [date]
**Team:** [team name]
**Total Services:** [n]
**Overall Health:** [n] Green | [n] Yellow | [n] Red

---

### Service Readiness Matrix

| Service | Oncall | Runbook | Monitoring | SLA Doc | Pipeline | Security | Overall |
|---------|--------|---------|------------|---------|----------|----------|---------|
| [name]  | [G/Y/R] | [G/Y/R] | [G/Y/R] | [G/Y/R] | [G/Y/R] | [G/Y/R] | [G/Y/R] |

---

### Red Services (Immediate Attention Required)

#### [Service Name]
- **Owner:** [engineer]
- **Status:** RED
- **Missing:**
  - [ ] [specific gap, e.g., "No oncall rotation assigned"]
  - [ ] [specific gap, e.g., "Runbook last updated 8 months ago"]
  - [ ] [specific gap]
- **Risk:** [what could go wrong]
- **Remediation:** [specific action items]
- **Target Date:** [when should this be fixed]

---

### Yellow Services (Plan to Address)

#### [Service Name]
- **Owner:** [engineer]
- **Status:** YELLOW
- **Gaps:**
  - [ ] [specific gap]
- **Remediation:** [action item]

---

### Ownership Clarity

| Service | Primary Owner | Backup Owner | Last Commit | Bus Factor |
|---------|--------------|--------------|-------------|------------|
| [name]  | [engineer]   | [engineer]   | [date]      | [n people] |

**Bus factor concerns (only 1 person knows the service):**
- [service]: only [engineer] has committed in past 6 months
- [service]: [engineer] is leaving/transferring

---

### Common Gaps Across Services
1. [e.g., "4/7 services lack canary monitoring"]
2. [e.g., "3/7 services have runbooks older than 6 months"]
3. [e.g., "2/7 services have no documented SLA"]

---

### Action Plan

| Priority | Action | Service | Owner | Due Date | Taskei Ticket |
|----------|--------|---------|-------|----------|---------------|
| P1 | [action] | [service] | [who] | [date] | [create/existing ID] |
| P2 | [action] | [service] | [who] | [date] | [create/existing ID] |

---

### Recommendations
1. [e.g., "Create Taskei tickets for all Red items, assign this sprint"]
2. [e.g., "Schedule knowledge transfer sessions for bus-factor-1 services"]
3. [e.g., "Add operational readiness checklist to service launch template"]
4. [e.g., "Review this audit monthly, target all-green within 2 sprints"]
```

## Delivery
Send the formatted report as a Slack DM to me. If any service is Red and actively serving production traffic, mark it as URGENT at the top of the message. Also create Taskei tickets for any Red items if they don't already exist (ask me before creating tickets).
