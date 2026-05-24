# Sprint Planning Preparation

Prepare a comprehensive sprint planning brief by gathering unfinished work from the current sprint, analyzing backlog readiness, calculating team capacity, and recommending a sprint goal.

## Data Sources
- Taskei (current sprint board, backlog, team member profiles)
- Calendar (PTO, holidays, recurring meetings for capacity calculation)
- CRUX CRs (in-flight code reviews that indicate work-in-progress)
- Slack DMs (recent context from engineers about blockers or carry-over items)

## Instructions
1. Query Taskei for all tasks in the current sprint that are not in "Done" status. Categorize them as:
   - In Progress (actively being worked on)
   - Blocked (has a blocker or dependency)
   - Not Started (was committed but never picked up)
2. For each unfinished task, check CRUX for any associated CRs to determine actual progress level.
3. Query Taskei backlog for items that are:
   - Estimated and ready for sprint (have acceptance criteria, story points, and no unresolved questions)
   - Needing grooming (missing estimates, unclear requirements, or stale > 30 days)
4. Calculate team capacity for the upcoming sprint:
   - Check calendar for each team member's PTO, holidays, and training days
   - Subtract recurring meeting load (estimated from calendar)
   - Apply standard 70% focus factor for available days
   - Output capacity in person-days and estimated story points (using team velocity)
5. Based on carry-over work, backlog priority, and capacity, recommend a sprint goal that is:
   - Achievable within calculated capacity
   - Aligned with current quarterly roadmap priorities
   - Specific and measurable

## Output Format
```
## Sprint Planning Brief - Sprint [N+1]

### Carry-Over from Sprint [N]
| Task ID | Title | Status | Assignee | Estimated Remaining Effort |
|---------|-------|--------|----------|---------------------------|

### Backlog Items Ready for Sprint
| Task ID | Title | Priority | Story Points | Dependencies |
|---------|-------|----------|--------------|--------------|

### Items Needing Grooming
| Task ID | Title | Issue | Suggested Action |
|---------|-------|-------|------------------|

### Team Capacity
| Team Member | Available Days | Adjusted Capacity (pts) | Notes |
|-------------|---------------|------------------------|-------|
| **Total** | X days | Y points | |

### Historical Velocity
- Last 3 sprints average: X points
- Recommended commitment: Y points (accounting for carry-over)

### Recommended Sprint Goal
[One clear, measurable statement]

### Risks & Considerations
- [List any risks to achieving the sprint goal]
```

## Delivery
Send the full report as a Slack DM to me at least 24 hours before the sprint planning ceremony. If any critical blockers are found on carry-over items, flag them immediately in a separate message.
