# Sev Ticket Review & Escalation Check

Review all open severity tickets owned by the team, assess blockers, check SLA compliance, and identify items needing escalation or management attention.

## Data Sources
- Taskei: Sev-tagged tickets, priority tickets, SLA metadata
- Oncall system: Active incidents, incident-to-ticket links, resolution status
- Slack: Discussions about sev tickets, blocker communications, escalation requests
- Email (Outlook): Escalation emails, customer communications about sev issues
- Pipelines: Fix deployments in progress for sev tickets

## Instructions
1. **Inventory Open Sev Tickets**:
   - Query Taskei for all open tickets with severity tags (Sev1, Sev2, Sev3) owned by team members
   - For each ticket, gather: title, severity, owner, age (days open), last update date, SLA deadline
   - Sort by severity (highest first), then by age (oldest first)
2. **SLA Compliance Check**:
   - For each sev ticket, check if it's within SLA:
     - Sev1: Resolution within [X hours/days per team SLA]
     - Sev2: Resolution within [X days per team SLA]
     - Sev3: Resolution within [X days per team SLA]
   - Flag any tickets approaching SLA breach (within 25% of remaining time)
   - Flag any tickets already in SLA breach
3. **Blocker Analysis**:
   - For each ticket, check:
     - Is it blocked on another team? (cross-team dependency)
     - Is it blocked on information? (waiting for customer data, reproduction steps)
     - Is it blocked on a decision? (needs architectural choice or approval)
     - Is it blocked on deployment? (fix ready but waiting for pipeline)
   - Check Slack for blocker discussions or requests for help
4. **Progress Assessment**:
   - When was each ticket last updated in Taskei?
   - Are there associated CRs in progress (fix being developed)?
   - Are there Pipelines deployments with the fix?
   - Is the owner actively working on it or is it stale?
5. **Escalation Determination**:
   - Identify tickets that need escalation: SLA breach, blocked on other teams, stale for >3 days
   - Determine escalation path: my intervention, peer manager, director, VP
   - Draft escalation message if needed
6. **Customer Impact Assessment**:
   - Which sev tickets have active customer impact?
   - Are there workarounds in place?
   - Is customer communication needed?

## Output Format
```
## Sev Ticket Review
### Team: {{TEAM_NAME}}
### Date: {{DATE}}
### Open Sev Tickets: [total count]

### IMMEDIATE ATTENTION REQUIRED
| Ticket | Sev | Age | SLA Status | Issue |
|--------|-----|-----|-----------|-------|
| [ID] | Sev1 | [X days] | BREACHED | [Brief description] |
| [ID] | Sev2 | [X days] | At Risk (Y% remaining) | [Brief description] |

### All Open Sev Tickets
#### Sev1 ([count] open)
| Ticket ID | Title | Owner | Age | SLA | Blocker | Last Update |
|-----------|-------|-------|-----|-----|---------|-------------|
| ... | ... | ... | ... | [OK/At Risk/Breached] | [None/Desc] | [date] |

#### Sev2 ([count] open)
| Ticket ID | Title | Owner | Age | SLA | Blocker | Last Update |
|-----------|-------|-------|-----|-----|---------|-------------|
| ... | ... | ... | ... | ... | ... | ... |

#### Sev3 ([count] open)
| Ticket ID | Title | Owner | Age | SLA | Blocker | Last Update |
|-----------|-------|-------|-----|-----|---------|-------------|
| ... | ... | ... | ... | ... | ... | ... |

### Blocked Tickets Needing Intervention
| Ticket | Blocked On | Duration Blocked | Suggested Action |
|--------|-----------|-----------------|-----------------|
| [ID] | [Team X response] | [X days] | [Escalate to their manager] |
| [ID] | [Decision needed] | [X days] | [Schedule decision meeting] |

### Stale Tickets (No Update >3 Days)
| Ticket | Owner | Last Update | Suggested Action |
|--------|-------|-------------|-----------------|
| ... | ... | ... | [Check in with owner in 1:1] |

### Fix Deployment Status
| Ticket | CR Status | Pipeline Stage | ETA to Production |
|--------|-----------|---------------|-------------------|
| ... | [In Review/Approved/Merged] | [Building/Canary/Prod] | ... |

### Escalation Actions Needed
1. **[Ticket ID]**: Escalate to [person/team] because [reason]. Draft message: "[suggested escalation text]"

### Trends
- New sev tickets this week: [count]
- Resolved this week: [count]
- Avg resolution time (last 30 days): [X days]
- Trend: [Improving/Stable/Worsening]
```

## Delivery
Send as a Slack DM to me daily at 9:00 AM. If any Sev1 ticket is in SLA breach or a new Sev1 is opened, send an immediate alert regardless of time.
