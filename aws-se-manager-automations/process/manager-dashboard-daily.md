# Daily Manager Dashboard

All-in-one daily briefing combining the top signals from all categories into a single digestible report for a 5-minute morning scan.

## Data Sources
- Taskei: Sprint progress, blocked tasks, approaching deadlines
- CRUX CRs: Stale CRs, pending reviews, merge activity
- Pipelines: Active deployments, pipeline failures
- Apollo: Service health, active deployments
- Oncall system: Overnight incidents, current oncall status, open sev tickets
- Slack: Urgent messages requiring my attention, team activity overnight
- Calendar: Today's schedule, prep needed for meetings
- Email (Outlook): Urgent emails, escalations received overnight

## Instructions
1. **Overnight/Off-Hours Summary** (since my last active time):
   - Check oncall system: Any incidents overnight? Status? Need my attention?
   - Check Slack: Urgent DMs or mentions I haven't responded to
   - Check email: Escalations or urgent communications received
   - Check Pipelines/Apollo: Any deployment issues or service health alerts
2. **Today's Calendar at a Glance**:
   - List today's meetings with key context (who, what, prep needed)
   - Highlight any 1:1s today (trigger prep if not already done)
   - Identify available focus blocks
   - Flag if today is over-scheduled (>6 hours of meetings)
3. **Sprint Health Snapshot**:
   - Days remaining in sprint
   - Tasks completed vs. planned (on track?)
   - Any tasks at risk of not completing this sprint
   - Blocked tasks requiring my intervention
4. **Team Activity Pulse**:
   - Who's oncall today?
   - Anyone on PTO?
   - Any notable deployments planned today?
   - Open sev tickets and their status
5. **Code Review Pipeline**:
   - CRs waiting >24 hours for review (needs attention)
   - CRs I need to review
   - CRs about to merge (awareness of what's shipping today)
6. **Action Items for Today**:
   - Items from previous 1:1s I committed to that are due
   - Escalations I need to make
   - Follow-ups promised to stakeholders
   - Decisions the team is waiting on from me
7. **Key Metrics Quick Glance** (no detail, just signals):
   - Service health: All green? Any amber/red?
   - Team velocity this sprint: On pace?
   - Open sev tickets: Count and trend direction

## Output Format
```
## Daily Dashboard: {{DATE}} ({{DAY_OF_WEEK}})
### Good morning. Here's your 5-minute briefing.

---

### Overnight Summary
| Category | Status | Action Needed |
|----------|--------|---------------|
| Incidents | [None / X incidents] | [No / Yes - details] |
| Urgent Slack | [None / X messages] | [No / Yes - from whom] |
| Urgent Email | [None / X emails] | [No / Yes - from whom] |
| Service Health | [All green / Issues] | [No / Yes - which service] |

### Today's Schedule
| Time | Meeting | With | Prep Needed |
|------|---------|------|-------------|
| ... | ... | ... | [None / Review X / Prepare Y] |
**Focus time available: [X hours] | Meeting hours: [Y]**

### Team Status
- Oncall today: [Name]
- Out today: [Names or "nobody"]
- Deploying today: [Name - service, or "nothing planned"]

### Sprint Health ([X] days remaining)
- Progress: [X/Y] tasks complete ([Z%])
- At risk: [count] tasks - [brief list]
- Blocked (need me): [count] - [what's needed]

### Attention Needed
#### Stale CRs (waiting >24h for review)
- [CR title] by [author] - waiting on [reviewer] for [X hours]

#### CRs I Need to Review
- [CR title] by [author] - submitted [when]

#### Open Sev Tickets
- Sev[X]: [count] open | Oldest: [age] days | SLA status: [OK/At Risk]

### My Action Items Due Today
- [ ] [Action from 1:1 with Person]
- [ ] [Follow-up promised to stakeholder]
- [ ] [Decision team is waiting for]

### Key Signals (Glanceable)
- Service health: [All green / Amber: X / Red: X]
- Sprint pace: [On track / Behind by X tasks]
- Team morale signal: [No concerns / Watch: reason]
- Sev ticket trend: [Improving: X fewer / Stable / Worsening: X more]

---
### Top 3 Priorities for Today
1. [Most important thing to address]
2. [Second priority]
3. [Third priority]
```

## Delivery
Send as a Slack DM to me every weekday at 8:00 AM (before my first meeting). Keep it concise - this should be readable in under 5 minutes. If there are critical overnight incidents (Sev1/Sev2), send an immediate alert regardless of time rather than waiting for the morning briefing.
