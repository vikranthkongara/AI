# Team Process Compliance Check

Audit the team's adherence to agreed-upon processes and standards, identifying areas where compliance is slipping and coaching may be needed.

## Data Sources
- CRUX CRs: CR template usage, description quality, test evidence, reviewer assignment practices
- Taskei: Ticket hygiene (descriptions, acceptance criteria, status updates, labels)
- Pipelines: Deployment runbook adherence, pre-deployment checklist completion
- Apollo: Deployment annotation quality, rollback plan documentation
- Slack: Communication protocols followed (thread usage, channel conventions)
- Oncall system: Runbook usage during incidents, post-mortem completion rate

## Instructions
1. **Code Review Standards**:
   - Sample last 20 CRs from the team. For each, check:
     - Does it follow the CR template? (description, testing, rollback plan)
     - Is the description meaningful (not just "fix bug" or "updates")?
     - Are tests included or explicitly noted as not needed with justification?
     - Were appropriate reviewers assigned (not just rubber-stamp partners)?
     - Is the CR appropriately sized (< 400 lines ideal)?
   - Calculate compliance rate for each criterion
2. **Ticket Hygiene**:
   - Sample last 30 Taskei tickets created or updated by team. Check:
     - Do tickets have clear descriptions and acceptance criteria?
     - Are status transitions timely (not stuck in wrong state)?
     - Are labels/tags properly applied?
     - Are estimates provided where required?
     - Are tickets linked to parent epics/goals?
   - Identify worst offenders (no names, just patterns)
3. **Deployment Standards**:
   - Check last 10 deployments in Pipelines:
     - Was the deployment runbook followed?
     - Were pre-deployment checks completed?
     - Was the deployment annotated with context?
     - Was canary period respected?
     - Were metrics monitored post-deployment?
4. **Documentation Standards**:
   - Check for: design docs before implementation, updated runbooks, README currency
   - Are operational runbooks kept up to date after incidents reveal gaps?
5. **Incident Response**:
   - Check oncall system for last 5 incidents:
     - Was the runbook consulted?
     - Was the incident properly documented?
     - Was a post-mortem completed (for Sev2+)?
     - Were follow-up action items tracked in Taskei?
6. **Communication Protocols**:
   - Are Slack channel conventions being followed?
   - Are status updates provided at agreed cadence?

## Output Format
```
## Process Compliance Report
### Team: {{TEAM_NAME}}
### Period: Last 30 days

### Compliance Scorecard
| Process Area | Compliance Rate | Target | Status |
|-------------|----------------|--------|--------|
| CR template usage | [X%] | 90% | [Pass/Fail] |
| CR description quality | [X%] | 85% | [Pass/Fail] |
| Test inclusion | [X%] | 80% | [Pass/Fail] |
| Ticket hygiene | [X%] | 85% | [Pass/Fail] |
| Deployment runbook | [X%] | 95% | [Pass/Fail] |
| Post-mortem completion | [X%] | 100% | [Pass/Fail] |
| Documentation updates | [X%] | 75% | [Pass/Fail] |

### Areas of Strength
- [Process area where team excels, with examples]

### Areas Needing Attention
#### [Process Area 1]
- Current state: [What's happening]
- Gap: [What should be happening]
- Impact: [Why it matters]
- Suggested action: [Coaching approach, not punishment]

#### [Process Area 2]
- Current state: [What's happening]
- Gap: [What should be happening]
- Impact: [Why it matters]
- Suggested action: [Coaching approach]

### Trends (vs. Last Month)
- Improving: [Areas getting better]
- Declining: [Areas getting worse]
- Stable: [Areas unchanged]

### Recommended Actions
1. [Specific action]: Address in team meeting / 1:1 / documentation update
2. [Specific action]: Automate / add tooling / create template
3. [Specific action]: Reinforce in next retro
```

## Delivery
Send as a Slack DM to me on the first Monday of each month. Do not share with the team directly - I will decide how to address gaps constructively.
