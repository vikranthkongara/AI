# Recognition & Wins Tracker

Track wins and contributions worthy of recognition for a direct report, ensuring good work doesn't go unnoticed.

## Data Sources
- Taskei: Completed tasks, especially high-impact or ahead-of-schedule deliveries
- CRUX CRs: High-quality CRs, impactful code contributions, thorough reviews that caught issues
- Pipelines: Successful launches and deployments
- Oncall system: Incident heroics, fast resolution times, prevention of customer impact
- Slack: Public praise from teammates or partner teams, shout-outs in channels
- Email (Outlook): Customer feedback, stakeholder appreciation, leadership visibility

## Instructions
1. Query Taskei for tasks completed by {{ENGINEER_NAME}} in the last 30 days. Highlight:
   - Tasks completed ahead of schedule
   - High-complexity tasks delivered successfully
   - Tasks that unblocked others on the team
   - Cross-team deliverables that required extra coordination
2. Check CRUX CRs for the last 30 days:
   - Large or complex CRs that shipped cleanly
   - Reviews where they caught significant bugs or design issues
   - CRs that introduced meaningful improvements (performance, reliability, developer experience)
   - Mentoring-quality review comments on junior engineers' CRs
3. Check Pipelines for successful launches they drove or significantly contributed to.
4. Check oncall system for:
   - Incidents resolved quickly under their watch
   - Proactive fixes that prevented incidents
   - Operational improvements they implemented (new alarms, runbooks, automation)
5. Search Slack for:
   - Shout-outs or thanks directed at them from anyone
   - Times they helped unblock teammates
   - Knowledge sharing (answering questions, posting useful information)
   - Process improvement suggestions they made
6. Check email for any external praise or positive customer impact they contributed to.
7. Categorize wins by type: Delivery, Quality, Collaboration, Operations, Innovation, Mentoring.
8. For each win, note the best venue for recognition (team meeting, Slack channel, skip-level mention, peer bonus nomination).

## Output Format
```
## Recognition Tracker: {{ENGINEER_NAME}}
### Period: Last 30 days
### Total Wins Identified: [count]

### High-Impact Wins (Share with skip-level / broader org)
1. **[Win title]**: [Description with specific impact]
   - Evidence: [Link to CR/task/Slack message]
   - Recognition venue: [Where to celebrate this]

### Team-Level Wins (Recognize in team meeting / team channel)
1. **[Win title]**: [Description]
   - Evidence: [Link]
2. **[Win title]**: [Description]
   - Evidence: [Link]

### 1:1 Recognition (Acknowledge privately)
1. **[Win title]**: [Description]
   - Why it matters: [Impact or growth signal]

### Win Categories
- Delivery: [count] wins
- Quality: [count] wins
- Collaboration: [count] wins
- Operations: [count] wins
- Innovation: [count] wins
- Mentoring: [count] wins

### Suggested Recognition Actions
- [ ] Mention [specific win] in next team meeting
- [ ] Post shout-out in [team Slack channel] for [specific contribution]
- [ ] Include [specific achievement] in next skip-level update
- [ ] Nominate for [peer bonus/spot award] for [specific impact]

### Praise Quotes from Others
- "[Quote from teammate/stakeholder]" - [Source, anonymized if needed]
```

## Delivery
Send as a Slack DM to me weekly on Monday morning so I can plan recognition activities for the week.
