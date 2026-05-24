# CR Queue Health Report

Report on code reviews pending review for more than 24 hours, CRs with open comments, and CRs that are blocking other work.

## Data Sources
- **CRUX CRs**: All open code reviews for team members (both authored and assigned for review)
- **Taskei**: Tickets linked to CRs to determine blocking relationships
- **Slack**: Any messages where engineers pinged reviewers for CR attention

## Instructions

1. **Query all open CRs** for team members (both as authors and as reviewers).

2. **Identify stale CRs (pending review >24h)**:
   - CRs where no reviewer has provided feedback for more than 24 hours
   - CRs where a revision was published but reviewers haven't re-reviewed in 24h
   - Sort by age (oldest first)

3. **Identify CRs with unresolved comments**:
   - CRs that have open/unresolved review comments
   - How long those comments have been open
   - Whether the author has responded

4. **Identify blocking CRs**:
   - CRs that are blocking Taskei tickets marked as dependencies
   - CRs that other CRs depend on (stacked CRs)
   - CRs blocking a deployment pipeline

5. **Calculate review load balance**:
   - How many open review requests each team member has
   - Who is overloaded vs who has capacity to take on more reviews

6. **Identify potential rubber-stamping**:
   - CRs approved in under 5 minutes for non-trivial changes (>100 lines)
   - Flag for awareness only

## Output Format

```
# CR Queue Health - [Date]

## Summary
- Total open CRs: [count]
- Pending review >24h: [count]
- Pending review >48h: [count] (URGENT)
- CRs with unresolved comments: [count]
- Blocking CRs: [count]

## Urgent: CRs Pending >48 Hours

| CR | Author | Title | Waiting Since | Assigned Reviewers |
|----|--------|-------|---------------|-------------------|
| CR-xxx | [name] | [title] | [hours]h | [names] |

## CRs Pending >24 Hours

| CR | Author | Title | Waiting Since | Assigned Reviewers |
|----|--------|-------|---------------|-------------------|
| CR-xxx | [name] | [title] | [hours]h | [names] |

## CRs With Unresolved Comments

| CR | Author | Open Comments | Oldest Comment | Status |
|----|--------|---------------|----------------|--------|
| CR-xxx | [name] | [count] | [age] | Waiting on author/reviewer |

## Blocking CRs (High Priority)
- [CR-xxx] "[title]" - Blocking [TASK-123] assigned to [engineer]
- [CR-yyy] "[title]" - Blocking deployment of [service]

## Review Load Distribution

| Reviewer | Assigned Reviews | Avg Review Time (24h) |
|----------|-----------------|----------------------|
| [name] | [count] | [hours]h |

## Recommended Actions
- Ask [reviewer] to prioritize CR-xxx (blocking [engineer])
- Reassign CR-yyy reviews from [overloaded] to [available]
```

## Delivery
- Send as Slack DM to me daily at 10:00 AM
- If any CR has been pending >48h, include a nudge suggestion with the specific reviewer to ping
