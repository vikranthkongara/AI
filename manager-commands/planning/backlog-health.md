# Backlog Health Analysis

Perform a comprehensive backlog health check: ticket distribution by priority, stale ticket identification, missing estimates, and duplicate detection.

## Data Sources
- Taskei (all backlog items, creation dates, last-updated dates, labels, estimates)
- CRUX CRs (linked CRs that may indicate work already done for a ticket)
- Slack DMs (recent discussions that may relate to undocumented work)

## Instructions
1. Query Taskei for all items in the backlog (not in active sprint, not completed). Collect:
   - Task ID, title, priority, creation date, last updated date
   - Story point estimate (if present)
   - Labels/tags
   - Assignee (if any)
   - Description completeness (has acceptance criteria, has description > 50 chars)
2. Generate distribution analysis:
   - Count by priority (Critical, High, Medium, Low, None)
   - Count by age bracket (< 1 week, 1-4 weeks, 1-3 months, 3-6 months, > 6 months)
   - Count by label/category
3. Identify stale tickets:
   - Not updated in > 60 days
   - Created > 90 days ago with no activity
   - Assigned to engineers who have left the team
4. Identify tickets without estimates:
   - No story points assigned
   - Group by priority (high-priority unestimated items are most concerning)
5. Identify poorly defined tickets:
   - Missing acceptance criteria
   - Description < 50 characters
   - No labels or categorization
6. Detect potential duplicates:
   - Tickets with similar titles (fuzzy match)
   - Tickets referencing the same service/component with similar descriptions
   - Flag for manual review rather than auto-deduplication
7. Check CRUX for any CRs that reference backlog ticket IDs to find tickets where work may already be complete but the ticket was never closed.
8. Calculate backlog health score (0-100) based on:
   - % of tickets estimated
   - % of tickets well-defined
   - % of tickets not stale
   - Priority distribution (inverted pyramid is healthy)

## Output Format
```
## Backlog Health Report
**Date:** [Date]
**Total Backlog Items:** [N]
**Health Score:** [X]/100

### Priority Distribution
| Priority | Count | % of Backlog | Trend vs Last Report |
|----------|-------|--------------|---------------------|
| Critical | [N]   | [X]%         | [+/-N]              |
| High     | [N]   | [X]%         | [+/-N]              |
| Medium   | [N]   | [X]%         | [+/-N]              |
| Low      | [N]   | [X]%         | [+/-N]              |
| None     | [N]   | [X]%         | [+/-N]              |

### Age Distribution
| Age Bracket | Count | % |
|-------------|-------|---|
| < 1 week    | [N]   | [X]% |
| 1-4 weeks   | [N]   | [X]% |
| 1-3 months  | [N]   | [X]% |
| 3-6 months  | [N]   | [X]% |
| > 6 months  | [N]   | [X]% |

### Stale Tickets (Recommend Close or Re-evaluate)
| Task ID | Title | Age | Last Updated | Suggested Action |
|---------|-------|-----|--------------|-----------------|
[Top 15 stalest tickets]

### Tickets Missing Estimates (High/Critical Priority)
| Task ID | Title | Priority | Age | Assignee |
|---------|-------|----------|-----|----------|

### Poorly Defined Tickets
| Task ID | Title | Issue | Suggested Fix |
|---------|-------|-------|---------------|

### Potential Duplicates
| Ticket A | Ticket B | Similarity | Recommendation |
|----------|----------|-----------|----------------|

### Tickets with Completed Work (Close Candidates)
| Task ID | Title | Related CR | CR Status |
|---------|-------|-----------|-----------|

### Grooming Recommendations
1. [Prioritized action: e.g., "Close 12 stale low-priority tickets"]
2. [Prioritized action: e.g., "Estimate 8 high-priority tickets in next grooming"]
3. [Prioritized action: e.g., "Review 3 potential duplicate pairs"]

### Health Score Breakdown
| Factor | Score | Weight | Weighted Score |
|--------|-------|--------|----------------|
| Estimated | [X]% | 30% | [Y] |
| Well-defined | [X]% | 25% | [Y] |
| Not stale | [X]% | 25% | [Y] |
| Priority balance | [X]% | 20% | [Y] |
| **Total** | | | **[Z]/100** |
```

## Delivery
Send the full report as a Slack DM to me every other Friday (before backlog grooming sessions). If the health score drops below 60, send an immediate alert with the top 3 actions to improve it.
