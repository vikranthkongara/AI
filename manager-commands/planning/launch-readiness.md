# Launch Readiness Check

Verify pre-launch readiness across all dimensions: monitoring, runbooks, load testing, rollback plans, security review, and stakeholder sign-offs.

## Data Sources
- Taskei (launch checklist tasks, blocker tickets)
- Pipelines (deployment pipeline status, stage gates)
- Apollo (deployment configuration, rollback mechanisms)
- Oncall system (monitoring and alerting configuration)
- CRUX CRs (pending code changes blocking launch)
- Email/Outlook (stakeholder approvals, security review status)
- Calendar (launch date, go/no-go meeting)

## Instructions
1. Query Taskei for the launch checklist associated with the upcoming release. Check each item's status.
2. Verify monitoring readiness:
   - Check oncall system for alarms configured on the launching service
   - Verify dashboards exist for key metrics (latency, errors, throughput, saturation)
   - Confirm alerting thresholds are set appropriately
   - Check that oncall rotation is staffed for launch window
3. Verify runbook readiness:
   - Check that runbooks exist for all critical alarms
   - Verify runbooks have been reviewed/updated recently
   - Confirm escalation paths are documented
4. Check deployment readiness:
   - Verify Pipeline stages are green up to the launch gate
   - Check Apollo deployment configuration (canary settings, bake time, auto-rollback)
   - Confirm rollback plan is documented and tested
   - Verify feature flags or kill switches are in place
5. Check testing readiness:
   - Load testing completed and results documented
   - Integration tests passing
   - Security review completed (check email for approval)
   - Accessibility review completed (if applicable)
6. Check stakeholder readiness:
   - Required approvals received (via email or Taskei)
   - Customer communication prepared (if customer-facing)
   - Documentation updated
   - Support team briefed
7. Identify any blocking CRs in CRUX that must merge before launch.
8. Calculate an overall launch readiness score.

## Output Format
```
## Launch Readiness Report
**Service/Feature:** [Name]
**Planned Launch Date:** [Date]
**Go/No-Go Meeting:** [Date/Time]
**Overall Readiness:** [X]% - [READY / NOT READY / CONDITIONAL]

### Readiness Checklist

#### Monitoring & Observability
| Item | Status | Details |
|------|--------|---------|
| Key metrics dashboards | [Done/Missing] | [Link or gap] |
| Latency alarms | [Done/Missing] | [Threshold] |
| Error rate alarms | [Done/Missing] | [Threshold] |
| Throughput alarms | [Done/Missing] | [Threshold] |
| Custom business metric alarms | [Done/Missing] | [Details] |
| Oncall rotation staffed | [Done/Missing] | [Who's on] |

#### Runbooks & Operations
| Item | Status | Details |
|------|--------|---------|
| Runbooks for critical paths | [Done/Missing] | [Links] |
| Escalation path documented | [Done/Missing] | |
| Rollback runbook | [Done/Missing] | [Link] |
| Known issues documented | [Done/Missing] | |

#### Deployment & Rollback
| Item | Status | Details |
|------|--------|---------|
| Pipeline stages green | [Done/Blocked] | [Stage status] |
| Canary configuration | [Done/Missing] | [% and duration] |
| Auto-rollback enabled | [Done/Missing] | [Trigger conditions] |
| Feature flags in place | [Done/Missing/N/A] | [Flag names] |
| Rollback tested | [Done/Missing] | [Last tested date] |

#### Testing
| Item | Status | Details |
|------|--------|---------|
| Load testing | [Done/Missing] | [Peak TPS tested] |
| Integration tests | [Passing/Failing] | [Pass rate] |
| Security review | [Approved/Pending/Missing] | [Reviewer] |
| Accessibility review | [Done/Missing/N/A] | |

#### Stakeholder Approvals
| Stakeholder | Approval Status | Date |
|-------------|----------------|------|

#### Blocking Items
| Item | Type | Owner | ETA |
|------|------|-------|-----|
[CRs, tasks, or approvals blocking launch]

### Risk Assessment
| Risk | Likelihood | Impact | Mitigation |
|------|-----------|--------|------------|

### Launch Recommendation
[READY TO LAUNCH / NOT READY - specific blockers / CONDITIONAL - items to resolve]

### If Launching - Key Dates
- Pre-launch: [Checklist of day-before actions]
- Launch day: [Step-by-step plan]
- Post-launch: [Monitoring plan for first 24/48/72 hours]
```

## Delivery
Send the full report as a Slack DM to me 72 hours before the planned launch date, then an updated version 24 hours before. Send immediate alerts if any critical blocking item is discovered.
