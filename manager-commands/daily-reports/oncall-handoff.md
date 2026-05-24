# Oncall Handoff Summary

Summarize oncall incidents from the last shift, pending tickets, runbook gaps identified, and prepare the incoming oncall engineer.

## Data Sources
- **Oncall System**: All pages, incidents, and escalations from the last oncall shift
- **Taskei**: Oncall-generated tickets and their current status
- **Slack**: Oncall channel messages and threads from the shift
- **Apollo**: Any deployment-related incidents or rollbacks during the shift
- **Pipelines**: Pipeline failures that triggered oncall engagement

## Instructions

1. **Pull all oncall events from the last shift** (typically 24h or 7-day rotation depending on schedule):
   - Total pages received
   - Severity breakdown (SEV1, SEV2, SEV3, informational)
   - Time to acknowledge for each page
   - Time to resolve for each incident
   - Any escalations to secondary or management

2. **Categorize incidents**:
   - Actionable vs noise (false alarms, auto-resolved)
   - Root cause categories (deployment, infrastructure, dependency, traffic spike, code bug)
   - Customer-impacting vs internal-only

3. **Identify pending items**:
   - Incidents still being monitored
   - Follow-up tickets created but not yet resolved
   - Temporary mitigations in place that need permanent fixes
   - Rollbacks that need to be re-deployed after fix

4. **Check for runbook gaps**:
   - Incidents where the oncall had to improvise (no runbook existed)
   - Runbooks that were followed but didn't resolve the issue
   - New failure modes not covered by existing documentation

5. **Assess oncall burden**:
   - Total pages during sleep hours (10 PM - 7 AM)
   - Longest incident duration
   - Whether oncall was paged for the same issue multiple times (duplicate pages)

6. **Prepare handoff notes for incoming oncall**:
   - What to watch for in the next shift
   - Any services in degraded state
   - Pending deployments that might cause issues

## Output Format

```
# Oncall Handoff Summary - [Date]
## Shift: [Start Date/Time] to [End Date/Time]
## Outgoing: [Engineer Name] | Incoming: [Engineer Name]

## Shift Summary
- Total pages: [count]
- Actionable: [count] | Noise: [count]
- SEV1: [count] | SEV2: [count] | SEV3: [count]
- Pages during sleep hours: [count]
- Mean time to acknowledge: [minutes]
- Mean time to resolve: [minutes]

## Incidents

### [Incident Title] - SEV[X]
- **Time**: [start] - [end] ([duration])
- **Service**: [affected service]
- **Impact**: [customer impact description]
- **Root Cause**: [brief root cause]
- **Resolution**: [what was done]
- **Follow-up**: [TASK-xxx] - [description]
- **Runbook used**: [Yes/No - link if yes]

## Pending Items for Incoming Oncall
- [ ] Monitor [service] - temp mitigation in place, permanent fix in CR-xxx
- [ ] [Service] deployment paused - resume after [condition]
- [ ] Follow up on TASK-xxx with [team] for root cause

## Runbook Gaps Identified
- No runbook for [scenario] - [TASK-xxx] created to document
- [Runbook link] needs update for [new failure mode]

## Noise Reduction Opportunities
- [Alarm name] fired [X] times - threshold may need tuning
- [Alarm name] auto-resolved every time - consider suppression or removal

## Oncall Health
- Sleep interruptions: [count]
- Toil ratio: [actionable/total pages]%
- Repeated pages for same issue: [Yes/No - details]
- Recommendation: [OK / Consider adding secondary / Review alarm thresholds]
```

## Delivery
- Send as Slack DM to me at the start of each new oncall rotation
- Also post a summary to the team oncall channel
- If there were any SEV1 incidents, flag them at the top of the message
