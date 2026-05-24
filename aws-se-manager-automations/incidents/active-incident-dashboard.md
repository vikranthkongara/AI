# Active Incident Dashboard

Provide a real-time status overview of all active incidents involving team-owned services, including severity, duration, ownership, and customer impact.

## Data Sources
- Oncall system (active incidents, severity levels, timeline, assigned responders)
- Pipelines (recent deployments that may correlate with incidents)
- Apollo (deployment status, rollback activity)
- Slack DMs (incident channel updates, responder communications)
- Email/Outlook (incident notifications, customer impact reports)

## Instructions
1. Query the oncall system for all active incidents (not resolved) involving services owned by the team.
2. For each active incident, collect:
   - Incident ID and title
   - Severity level (Sev1/Sev2/Sev3/Sev4/Sev5)
   - Start time and current duration
   - Assigned incident commander and responders
   - Current status (Investigating, Identified, Mitigating, Monitoring)
   - Affected services and customer impact
3. Check Pipelines and Apollo for recent deployments to affected services:
   - Was there a deployment in the last 6 hours before incident start?
   - Has a rollback been initiated?
   - What is the rollback status?
4. For each incident, assess:
   - Is the incident getting better or worse (trend)?
   - Are the right people engaged?
   - Does it need escalation?
   - Is there a communication gap (last update > 30 minutes for Sev1/2)?
5. Check for related incidents (multiple services affected may indicate a common root cause).
6. Check email for any customer-reported issues that haven't been linked to an incident yet.
7. Calculate team incident load: how many engineers are currently pulled into incident response vs available for planned work.

## Output Format
```
## Active Incident Dashboard
**Last Updated:** [Timestamp]
**Active Incidents:** [N]
**Engineers in Incident Response:** [N]/[Total Team]

### Critical/High Severity (Sev1-2)

#### [Incident ID] - [Title]
- **Severity:** [Sev Level]
- **Status:** [Investigating/Identified/Mitigating/Monitoring]
- **Duration:** [X hours Y minutes]
- **Impact:** [Customer-facing impact description]
- **Services Affected:** [List]
- **Incident Commander:** [Name]
- **Responders:** [Names]
- **Last Update:** [Time] - [Summary of last update]
- **Recent Deployment:** [Yes/No - details if yes]
- **Rollback Status:** [N/A / Initiated / Completed / Not needed]
- **Trend:** [Improving / Stable / Worsening]
- **Needs Attention:** [Yes/No - why]

### Medium/Low Severity (Sev3-5)

| Incident ID | Title | Severity | Duration | Status | Owner | Impact |
|-------------|-------|----------|----------|--------|-------|--------|

### Correlation Analysis
| Pattern | Incidents | Possible Common Cause |
|---------|-----------|----------------------|

### Recent Deployments to Affected Services
| Service | Deploy Time | Pipeline | Deployer | Potentially Related |
|---------|-------------|----------|----------|-------------------|

### Team Impact
| Engineer | Incident Role | Planned Work Affected | Duration Engaged |
|----------|--------------|----------------------|-----------------|

### Action Items
- [Immediate actions needed]
- [Escalation recommendations]
- [Communication gaps to address]

### Incident Timeline (Last 24 Hours)
| Time | Event | Incident |
|------|-------|----------|
[Key events in chronological order]
```

## Delivery
Send the dashboard as a Slack DM to me immediately when queried, and auto-refresh every 30 minutes during active Sev1/2 incidents. Send an immediate alert when any new Sev1 or Sev2 incident is opened involving team services.
