# Team Working Agreements Audit

Check adherence to the team's agreed-upon working norms and response time commitments, identifying where norms are drifting and may need reinforcement or revision.

## Data Sources
- Slack: Response times to requests, channel convention adherence, status update cadence
- CRUX CRs: Review turnaround times, review quality expectations, CR size guidelines
- Taskei: Ticket update frequency, status transition timeliness, estimation practices
- Calendar: Meeting punctuality signals, agenda preparation
- Oncall system: Escalation protocol adherence, handoff quality

## Instructions
1. **CR Review Expectations**:
   - Team norm: Reviews completed within [X hours/days]
   - Measure actual review turnaround for last 2 weeks
   - Identify: Who consistently meets the norm? Who doesn't?
   - Check: Are CRs sized appropriately per team guidelines (< [X] lines)?
   - Check: Are required reviewers being included?
2. **Communication Response Times**:
   - Team norm: Respond to team channel messages within [X hours]
   - Team norm: Respond to DMs within [X hours]
   - Team norm: Acknowledge oncall escalations within [X minutes]
   - Measure actual response times per team member
   - Identify patterns: specific times/days where norms slip
3. **Documentation Requirements**:
   - Team norm: Design docs required for work > [X] story points
   - Team norm: Runbooks updated when operations change
   - Team norm: README kept current
   - Check: Were design docs written for qualifying work?
   - Check: Were runbooks updated after recent incidents?
4. **Status Update Cadence**:
   - Team norm: Task status updated [daily/every-X-days]
   - Team norm: Sprint standup updates provided [frequency]
   - Measure actual update frequency per person
   - Identify stale tickets (no update in > [X] days)
5. **Meeting Norms**:
   - Team norm: Agendas shared [X hours] before meetings
   - Team norm: Meetings start/end on time
   - Team norm: Action items documented and tracked
   - Check adherence to these norms
6. **Oncall Norms**:
   - Team norm: Oncall handoff notes provided
   - Team norm: Pages acknowledged within [X minutes]
   - Team norm: Post-mortems completed within [X days] for Sev2+
   - Check actual adherence
7. **Assess Norm Health**:
   - For each norm, determine: universally followed, mostly followed, frequently violated, or abandoned in practice
   - For violated norms: Is the norm wrong (needs updating) or is adherence the issue?

## Output Format
```
## Team Norms Audit
### Team: {{TEAM_NAME}}
### Period: Last 2 weeks
### Norms Assessed: [count]

### Norm Adherence Scorecard
| Norm | Target | Actual | Adherence | Status |
|------|--------|--------|-----------|--------|
| CR review turnaround | < 24 hrs | [avg] hrs | [X%] | [Green/Yellow/Red] |
| CR size limit | < 400 lines | [avg] lines | [X%] | [Green/Yellow/Red] |
| Slack response (team channel) | < 4 hrs | [avg] hrs | [X%] | [Green/Yellow/Red] |
| Task status updates | Every 2 days | [avg] days | [X%] | [Green/Yellow/Red] |
| Design doc for large work | Always | [X/Y cases] | [X%] | [Green/Yellow/Red] |
| Oncall handoff notes | Always | [X/Y handoffs] | [X%] | [Green/Yellow/Red] |
| Post-mortem completion | Within 5 days | [avg] days | [X%] | [Green/Yellow/Red] |
| Meeting agendas shared | 24 hrs prior | [X%] met | [X%] | [Green/Yellow/Red] |

### Norms Working Well (Green)
- [Norm]: Team consistently adheres, no action needed

### Norms Drifting (Yellow)
- **[Norm]**: Adherence at [X%], down from typical. 
  - Pattern: [When/where it slips]
  - Likely cause: [Increased workload / unclear expectation / tooling friction]
  - Suggested action: [Gentle reminder / process change / tooling improvement]

### Norms Failing (Red)
- **[Norm]**: Adherence at [X%], significantly below target.
  - Analysis: Is the norm still appropriate, or does it need revision?
  - If norm is good: [How to reinforce - team discussion, tooling, accountability]
  - If norm needs revision: [Suggested new norm and why]

### Norms to Consider Retiring
- [Norm that nobody follows and may not be serving the team anymore]
- Reason: [Why it might be outdated or impractical]

### Norms to Consider Adding
- [Gap observed]: Team would benefit from a norm around [behavior]
- Evidence: [What prompted this observation]

### Recommended Actions
1. [Action for team meeting discussion]
2. [Action for 1:1 coaching]
3. [Action for tooling/automation to enforce norms]
```

## Delivery
Send as a Slack DM to me bi-weekly on Mondays. Use this to inform retro discussions and 1:1 coaching conversations.
