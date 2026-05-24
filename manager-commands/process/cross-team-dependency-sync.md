# Cross-Team Dependency Sync Preparation

Prepare for cross-team synchronization meetings by compiling the status of shared dependencies, blockers to escalate, and commitments to confirm.

## Data Sources
- Taskei: Dependency tickets (ours on others, others on us), cross-team work items
- CRUX CRs: Cross-team code contributions, shared library changes, API changes
- Pipelines: Shared pipeline dependencies, deployment coordination needs
- Slack: Cross-team channel discussions, coordination threads, escalation signals
- Email (Outlook): Cross-team agreements, commitment emails, escalation threads
- Calendar: Upcoming cross-team milestones, shared deadlines

## Instructions
1. **Dependencies We Have on Other Teams**:
   - Query Taskei for our tasks blocked on or waiting on other teams
   - For each dependency:
     - What's the current status? (Check Slack, email for recent updates)
     - When was it last updated by the other team?
     - Is it on track for our needed timeline?
     - Is escalation needed?
   - Check CRUX for any CRs we're waiting on other teams to review or merge
2. **Dependencies Others Have on Us**:
   - Query Taskei for our tasks that other teams are waiting on
   - For each commitment:
     - Are we on track to deliver by the agreed date?
     - If at risk, what's the revised ETA?
     - Do we need to communicate a slip early?
   - Check CRs that other teams are waiting for us to review
3. **Shared Infrastructure & Services**:
   - Check Pipelines for any shared deployment dependencies
   - Check Apollo for shared service health that affects multiple teams
   - Identify any upcoming breaking changes (API deprecations, library upgrades) that need coordination
4. **Communication Health**:
   - When was the last meaningful update exchanged with each partner team?
   - Are there stale coordination threads that need revival?
   - Any miscommunications or misaligned expectations detected?
5. **Upcoming Coordination Needs**:
   - Check calendar for upcoming milestones that require cross-team coordination
   - Identify any upcoming deployments that need joint coordination
   - Flag any capacity conflicts (both teams planning major work at same time)
6. **Risks & Escalations**:
   - Identify dependencies at risk of missing agreed timelines
   - Draft escalation messages for any blocked items
   - Prepare compromise proposals if timelines need to shift

## Output Format
```
## Cross-Team Dependency Sync Prep
### Meeting: {{MEETING_NAME}}
### Date: {{DATE}}
### Partner Team(s): {{TEAM_NAMES}}

### Summary Status
- Dependencies on them: [X total], [Y on track], [Z at risk]
- Dependencies from them on us: [X total], [Y on track], [Z at risk]
- Escalations needed: [count]

### Dependencies We Have on {{PARTNER_TEAM}}
| Item | Their Owner | Our Need-By | Status | Last Update | Action Needed |
|------|-------------|-------------|--------|-------------|---------------|
| ... | [Person] | [Date] | [On track/At risk/Blocked] | [Date] | [Ask/Escalate/OK] |

### Commitments We Owe {{PARTNER_TEAM}}
| Item | Our Owner | Promised By | Status | Notes |
|------|-----------|-------------|--------|-------|
| ... | [Person] | [Date] | [On track/At risk/Slip] | [If slipping, new ETA] |

### Blockers to Raise
1. **[Blocker]**: We've been waiting [X days] for [thing]. Impact: [what it blocks for us]. Ask: [specific request].
2. **[Blocker]**: [Same structure]

### Slips to Communicate (Our Commitments at Risk)
1. **[Commitment]**: Original date [X], revised to [Y] because [reason]. Mitigation: [what we're doing to minimize impact].

### Upcoming Coordination Needs
| What | When | Teams Involved | Coordination Action |
|------|------|---------------|-------------------|
| [Joint deployment] | [Date] | [Teams] | [What needs to happen] |
| [API migration] | [Date range] | [Teams] | [What needs to happen] |

### Shared Service Health
| Service | Owner | Current Health | Issues |
|---------|-------|---------------|--------|
| [Shared service] | [Team] | [Healthy/Degraded] | [Any issues affecting us] |

### Discussion Agenda (Suggested)
1. [Most urgent blocker to unblock]
2. [Timeline alignment for upcoming milestone]
3. [New dependency to establish/negotiate]
4. [FYI items for awareness]

### Preparation Notes for Me
- Tone: [Collaborative/Firm - depending on situation]
- Key ask: [The one thing I need to walk away with]
- What I can offer: [Trade or help that might unblock their willingness]
```

## Delivery
Send as a Slack DM to me 2 hours before any scheduled cross-team sync meeting (check calendar for meeting times and attendees to identify the relevant partner team).
