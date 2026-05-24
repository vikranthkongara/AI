# Morning Standup Prep

Gather what each team member worked on yesterday (from CRs, Taskei updates) and compile standup notes for the engineering manager.

## Data Sources
- **CRUX CRs**: All code reviews created, updated, or merged by team members in the last 24 hours
- **Taskei**: Task status changes, comments, and updates from yesterday
- **Pipelines**: Any deployments initiated by team members
- **Oncall System**: Pages or incidents handled by the on-call engineer
- **Slack**: Any relevant channel updates or threads mentioning blockers

## Instructions

1. **Identify team roster**: Pull the current list of engineers on the team from the team directory or use the configured team member list.

2. **For each team member, gather**:
   - CRs authored yesterday (title, status, reviewers assigned)
   - CRs reviewed/approved yesterday
   - Taskei tickets moved to "In Progress," "In Review," or "Done" yesterday
   - Any comments they left on Taskei tickets indicating progress or blockers
   - Any deployments they initiated via Pipelines or Apollo
   - Oncall pages they responded to (if they are the current on-call)

3. **Identify blockers**:
   - Taskei tickets marked as "Blocked"
   - CRs with unresolved comments older than 24 hours
   - Any Slack messages where an engineer explicitly asked for help or flagged a dependency

4. **Compile the standup summary**:
   - Group by engineer
   - For each engineer list: what they completed, what they are working on today (inferred from in-progress tickets), and any blockers

5. **Flag items needing manager attention**:
   - Engineers with no visible activity in the last 24 hours (may be on PTO - cross-reference calendar)
   - Blockers that require escalation or cross-team coordination
   - CRs that have been open for more than 3 days without approval

## Output Format

```
# Morning Standup Prep - [Date]

## Team Summary
- CRs merged yesterday: [count]
- Tickets completed: [count]
- Active blockers: [count]
- Oncall incidents: [count]

## Per-Engineer Updates

### [Engineer Name]
**Yesterday:**
- [CR-12345] Merged: "Add retry logic to payment service"
- [TASK-678] Moved to Done: "Implement caching layer"

**Today (inferred):**
- [TASK-901] In Progress: "Write integration tests for caching"

**Blockers:**
- None / [Description of blocker]

---
(repeat for each engineer)

## Items Needing Manager Attention
- [Engineer A] has had no activity in 24h (not on PTO per calendar)
- [CR-45678] has been open 5 days with no reviewer response
- [Engineer B] is blocked on Team X for API access
```

## Delivery
- Send compiled report as a Slack DM to me by 8:45 AM local time, 15 minutes before standup
- If any critical blockers are found, flag them with a warning emoji at the top of the message
