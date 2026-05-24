# Blocker Radar

Identify team members who are blocked on their work, whether from Taskei blocked status, unanswered CR comments, waiting on external teams, or other impediments.

## Data Sources
- **Taskei**: Tickets with "Blocked" status or blocker tags
- **CRUX CRs**: CRs with unanswered questions or pending reviews from external teams
- **Slack**: Messages in team channels where engineers mentioned being stuck or waiting
- **Calendar**: Meetings scheduled to resolve blockers or dependency discussions
- **Email (Outlook)**: Threads with external teams that have gone unanswered

## Instructions

1. **Check Taskei for blocked tickets**:
   - All tickets with status "Blocked" or blocker flag set
   - What they are blocked on (dependency, approval, external team, resource)
   - How long they have been blocked
   - Who is responsible for unblocking

2. **Check CRs for unanswered review requests**:
   - CRs sent to reviewers outside the team that haven't received feedback in 24+ hours
   - CRs where the author asked a question in comments that hasn't been answered
   - CRs waiting on approval from a specific person who hasn't responded

3. **Check for external dependencies**:
   - Taskei tickets tagged with external team dependencies
   - Email threads with other teams that are awaiting response for 48+ hours
   - Slack threads in cross-team channels where team members are waiting for answers

4. **Check for resource blockers**:
   - Tickets blocked on AWS account access, permissions, or infrastructure provisioning
   - Tickets blocked on design approvals or architectural decisions
   - Tickets blocked on data or access from another team

5. **Assess blocker severity and age**:
   - How long each blocker has existed
   - Impact on sprint goals (is this blocking a sprint commitment?)
   - Whether there is a workaround available
   - Escalation path if not resolved soon

6. **Identify patterns**:
   - Same team blocking multiple items (systemic dependency)
   - Same person is a bottleneck for multiple approvals
   - Recurring blockers that suggest a process improvement opportunity

## Output Format

```
# Blocker Radar - [Date]

## Summary
- Team members currently blocked: [count]/[total]
- Total active blockers: [count]
- Avg blocker age: [days]
- Sprint commitments at risk due to blockers: [count]

## Critical Blockers (Sprint Commitments at Risk)

### [Engineer Name] - Blocked [X] days
- **Ticket**: [TASK-xxx] - "[title]"
- **Blocked on**: [description - e.g., "Waiting on Team Y for API access"]
- **Impact**: Blocks sprint goal "[goal name]"
- **Escalation**: [Suggested action - e.g., "Reach out to [manager] on Team Y"]
- **Workaround**: [Available/None]

## All Active Blockers

| Engineer | Ticket | Blocked On | Days Blocked | Category | Severity |
|----------|--------|-----------|--------------|----------|----------|
| [name] | TASK-xxx | [description] | [days] | External/Internal/Resource | High/Med/Low |

## Unanswered CR Reviews (External)

| CR | Author | External Reviewer | Waiting Since | Team |
|----|--------|-------------------|---------------|------|
| CR-xxx | [name] | [reviewer] | [hours]h | [team] |

## Unanswered Questions

| Location | Engineer | Question Summary | Asked | Waiting On |
|----------|----------|-----------------|-------|-----------|
| CR-xxx comment | [name] | [summary] | [date] | [person] |
| Slack #channel | [name] | [summary] | [date] | [team] |
| Email thread | [name] | [summary] | [date] | [person] |

## Blocker Patterns
- [Team X] is blocking [3] of our tickets - consider scheduling sync
- [Person Y] is reviewer bottleneck for [4] CRs - suggest alternate reviewer
- [Resource type] access requests taking avg [X] days - escalate process

## Recommended Manager Actions
1. [Most impactful action to unblock team]
2. [Second most impactful action]
3. [Third action]
```

## Delivery
- Send as Slack DM to me daily at 9:15 AM (before standup)
- If any new critical blocker is detected (blocking sprint commitment), send immediate alert
- Include a weekly trend on Fridays showing blocker count over time
