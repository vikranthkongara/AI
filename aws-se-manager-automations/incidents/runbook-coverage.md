# Runbook Coverage Analysis

Identify services and alarms without runbooks, flag outdated runbooks, and track whether runbooks were actually followed during incidents.

## Data Sources
- Oncall system (alarms, incident history, linked runbooks)
- Apollo (service inventory, alarm configurations)
- Taskei (runbook creation/update tasks)
- CRUX CRs (runbook document changes)
- Email/Outlook (incident retrospective notes)

## Instructions
1. Query the oncall system for a complete list of all alarms configured for team-owned services.
2. For each alarm, check if a runbook is linked:
   - Runbook exists and is linked to the alarm
   - Runbook exists but is not linked (discoverable but not easy to find during incident)
   - No runbook exists
3. For alarms with runbooks, assess runbook freshness:
   - Last updated date
   - Flag as stale if not updated in > 6 months
   - Flag as potentially outdated if the service has had significant changes (check CRUX for major refactors)
4. Analyze runbook usage during recent incidents:
   - For each incident in the past 60 days, was the runbook referenced?
   - Did the resolution follow the runbook steps?
   - Were there incidents where the runbook was insufficient (responder had to deviate)?
   - Were there incidents where no runbook existed and responders struggled?
5. Categorize missing runbooks by risk:
   - **Critical:** High-severity alarms without runbooks
   - **High:** Alarms that have fired in the past 30 days without runbooks
   - **Medium:** Alarms configured but never fired, no runbook
   - **Low:** Low-severity or informational alarms
6. Check Taskei for any existing tasks to create or update runbooks, and their status.
7. Identify runbook quality issues:
   - Runbooks that reference deprecated tools or outdated procedures
   - Runbooks without escalation paths
   - Runbooks without rollback instructions
   - Runbooks that are overly long (> 50 steps without clear decision trees)

## Output Format
```
## Runbook Coverage Report
**Date:** [Date]
**Total Alarms:** [N]
**Alarms with Runbooks:** [N] ([X]%)
**Coverage Target:** [Y]%

### Coverage Summary
| Category | Alarms | With Runbook | Coverage | Gap |
|----------|--------|--------------|----------|-----|
| Sev1-2 Critical | [N] | [N] | [X]% | [N missing] |
| Sev3 Standard | [N] | [N] | [X]% | [N missing] |
| Sev4-5 Low | [N] | [N] | [X]% | [N missing] |
| **Total** | [N] | [N] | [X]% | [N missing] |

### Critical Gaps (High-Severity Alarms Without Runbooks)
| Alarm | Service | Severity | Last Fired | Urgency |
|-------|---------|----------|-----------|---------|

### Recently Fired Alarms Without Runbooks
| Alarm | Service | Times Fired (30d) | Avg Resolution Time | Impact |
|-------|---------|-------------------|--------------------|---------| 

### Stale Runbooks (Not Updated > 6 Months)
| Runbook | Alarm | Last Updated | Service Changes Since | Risk |
|---------|-------|--------------|----------------------|------|

### Runbook Effectiveness (Last 60 Days)
| Incident | Runbook Used | Followed? | Sufficient? | Notes |
|----------|-------------|-----------|-------------|-------|

### Runbooks That Failed During Incidents
| Runbook | Incident | Failure Mode | Fix Needed |
|---------|----------|--------------|-----------|
[Cases where runbook was wrong, incomplete, or misleading]

### Runbook Quality Issues
| Runbook | Issue | Severity | Fix Required |
|---------|-------|----------|-------------|
| [Name] | Missing escalation path | High | Add escalation section |
| [Name] | References deprecated tool | Medium | Update tooling reference |
| [Name] | Too long (75 steps) | Medium | Add decision tree |

### Existing Improvement Tasks (Taskei)
| Task ID | Description | Status | Assignee | Due Date |
|---------|-------------|--------|----------|----------|

### Recommended Actions (Prioritized)
| Priority | Action | Alarm/Service | Suggested Owner | Effort |
|----------|--------|---------------|-----------------|--------|
| 1 (Critical) | Create runbook | [Alarm] | [Engineer] | [X hours] |
| 2 (Critical) | Create runbook | [Alarm] | [Engineer] | [X hours] |
| 3 (High) | Update stale runbook | [Runbook] | [Engineer] | [X hours] |

### Coverage Trend
| Month | Total Alarms | Coverage % | New Runbooks Created | Runbooks Updated |
|-------|-------------|-----------|---------------------|-----------------|
```

## Delivery
Send the full report as a Slack DM to me on the 1st of each month. Send immediate alerts when a Sev1/2 incident occurs on an alarm that has no runbook.
