# Technical Debt Ownership Report

Track which engineers are proactively paying down technical debt vs only shipping new features. This helps ensure tech debt work is recognized during performance reviews and distributed fairly across the team.

## Data Sources
- CRUX CRs: code review history, commit messages, CR descriptions tagged with refactoring/tech-debt
- Taskei: tickets labeled with tech-debt, refactoring, maintenance, or similar tags
- Pipelines: deployment history for non-feature changes
- Brazil Build System: test coverage changes per package, dependency version bumps

## Instructions

1. Query CRUX CRs for the past 30 days for all team members. Categorize each CR by type:
   - **Feature work:** new functionality, product requirements
   - **Tech debt reduction:** refactoring, removing dead code, simplifying architecture
   - **Test improvements:** adding tests, fixing flaky tests, increasing coverage
   - **Dependency updates:** version bumps, migrating deprecated APIs
   - **Operational improvements:** monitoring, alerting, logging, runbooks
   - **Documentation:** design docs, wikis, READMEs

   Use CR descriptions, commit messages, and linked Taskei tickets to categorize. Look for keywords: "refactor", "cleanup", "migrate", "deprecate", "tech debt", "test coverage", "flaky", "simplify", "remove unused".

2. Query Taskei for tickets tagged with tech-debt, maintenance, or operational-excellence categories. Track:
   - Who picked up these tickets voluntarily vs who was assigned
   - Completion rate on tech debt tickets vs feature tickets
   - Age of tech debt tickets (how long they sat before someone worked them)

3. From Brazil, check for:
   - Test coverage changes by package owner (increasing vs decreasing)
   - Dependency version freshness (who is keeping packages up to date)
   - Build time improvements from refactoring

4. Calculate per-engineer metrics:
   - Tech debt CR ratio: (tech debt CRs / total CRs) as percentage
   - Lines removed vs lines added ratio (high removal often indicates cleanup)
   - Voluntary tech debt pickup rate (self-assigned tech debt tickets)
   - Test coverage delta (net change in coverage for owned packages)

5. Compare against team averages and identify:
   - Engineers who consistently invest in code health (top quartile)
   - Engineers focused exclusively on features with zero tech debt work
   - Overall team tech debt investment rate (target: 15-20% of effort)

## Output Format

```
## Technical Debt Ownership Report
**Period:** Past 30 days
**Team average tech debt investment:** [%] of CRs

### Per-Engineer Breakdown

| Engineer | Total CRs | Tech Debt CRs | TD Ratio | Tests Added | Deps Updated | Voluntary Pickups |
|----------|-----------|---------------|----------|-------------|--------------|-------------------|
| [name]   | [n]       | [n]           | [%]      | [n]         | [n]          | [n]               |

### Top Tech Debt Contributors
1. **[name]** - [specific contributions: e.g., "Migrated 3 services off deprecated API, removed 2k lines of dead code"]
2. **[name]** - [specific contributions]
3. **[name]** - [specific contributions]

### Tech Debt Backlog Status
- Open tech debt tickets: [n] (up/down from last month)
- Average age of open tech debt tickets: [days]
- Tickets closed this month: [n]
- Net change: [+/- n tickets]

### Observations
- [Note patterns: e.g., "Tech debt work clustered in week 2, likely due to lighter sprint load"]
- [Flag if team is below 15% investment threshold]
- [Note if tech debt is concentrated in one person vs distributed]

### Recommendations
1. [e.g., "Consider dedicating one sprint day per week to tech debt"]
2. [e.g., "Recognize [engineer] in team meeting for consistent cleanup work"]
3. [e.g., "Assign tech debt tickets to [engineer] for development opportunity"]
```

## Delivery
Send the formatted report as a Slack DM to me. This report is for my eyes only and is used for performance review evidence gathering. Do not share with the team directly.
