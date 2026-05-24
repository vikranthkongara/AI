# Ticket Aging Report

Report on Taskei tickets that haven't been updated in 3+ days, tickets past their due dates, and stale work items that need attention.

## Data Sources
- **Taskei**: All tickets assigned to team members in active sprints and backlog
- **CRUX CRs**: Cross-reference to see if linked CRs have activity even if ticket wasn't updated
- **Calendar**: Check if assignees are on PTO (which would explain inactivity)

## Instructions

1. **Query all active Taskei tickets** assigned to team members (status: In Progress, In Review, To Do within current sprint).

2. **Identify stale tickets (no updates in 3+ days)**:
   - Tickets where no status change, comment, or linked CR activity in 3+ days
   - Exclude tickets where the assignee is on PTO (check calendar)
   - Categorize by staleness: 3-5 days, 5-7 days, 7+ days

3. **Identify overdue tickets**:
   - Tickets past their due date that are not in "Done" status
   - Calculate days overdue
   - Note original estimate vs actual time spent

4. **Identify tickets with no assignee**:
   - Tickets in the current sprint that are unassigned
   - Tickets that were unassigned when a team member left or moved

5. **Check for zombie tickets**:
   - Tickets marked "In Progress" for more than 2 weeks
   - Tickets that have been reopened multiple times
   - Tickets with scope creep (many added subtasks)

6. **Cross-reference with CRs**:
   - If a ticket has no Taskei update but has linked CR activity, note it as "active but not updated"
   - Suggest the engineer update their ticket

## Output Format

```
# Ticket Aging Report - [Date]

## Summary
- Stale tickets (3+ days no update): [count]
- Overdue tickets: [count]
- Unassigned in sprint: [count]
- Zombie tickets (2+ weeks in progress): [count]

## Critical: Overdue Tickets

| Ticket | Assignee | Title | Due Date | Days Overdue | Priority |
|--------|----------|-------|----------|--------------|----------|
| TASK-xxx | [name] | [title] | [date] | [days] | P1/P2 |

## Stale Tickets (7+ days - Urgent)

| Ticket | Assignee | Title | Last Update | Days Stale |
|--------|----------|-------|-------------|-----------|
| TASK-xxx | [name] | [title] | [date] | [days] |

## Stale Tickets (3-7 days)

| Ticket | Assignee | Title | Last Update | Days Stale | Has CR Activity? |
|--------|----------|-------|-------------|-----------|-----------------|
| TASK-xxx | [name] | [title] | [date] | [days] | Yes/No |

## Zombie Tickets (In Progress 2+ Weeks)

| Ticket | Assignee | Title | Started | Days In Progress | Notes |
|--------|----------|-------|---------|-----------------|-------|
| TASK-xxx | [name] | [title] | [date] | [days] | [context] |

## Unassigned Sprint Tickets

| Ticket | Title | Priority | Sprint | Notes |
|--------|-------|----------|--------|-------|
| TASK-xxx | [title] | [priority] | [sprint] | [context] |

## Recommended Actions
- 1:1 with [engineer] about TASK-xxx (7 days stale, P1 priority)
- Reassign TASK-yyy or break into smaller tasks (zombie, 3 weeks)
- Ping [engineer] to update TASK-zzz (has CR activity but ticket not updated)
```

## Delivery
- Send as Slack DM to me daily at 9:30 AM
- On Fridays, include a weekly trend showing whether ticket aging is improving or worsening
