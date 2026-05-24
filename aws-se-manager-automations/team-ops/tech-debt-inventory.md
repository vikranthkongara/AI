# Tech Debt Inventory Report

Perform a comprehensive scan of the team's codebase and project tracking to identify and catalog technical debt: TODO comments, suppressed lint warnings, deprecated API usage, known tech debt tickets, and code quality concerns.

## Data Sources
- Brazil Build System: package source code, build warnings, deprecated dependency usage
- CRUX CRs: recent changes with tech debt indicators, deferred improvements noted in reviews
- Taskei: tickets tagged with tech-debt, maintenance, cleanup, or technical-improvement
- Pipelines: build warnings, test coverage reports, static analysis results
- Oncall system: recurring alerts that indicate underlying tech debt

## Instructions

1. Scan the team's Brazil packages for code-level tech debt signals:
   - TODO/FIXME/HACK/XXX comments (count per package, note any with dates or ticket references)
   - Suppressed lint warnings (@SuppressWarnings, # noqa, // nolint, eslint-disable)
   - Deprecated API usage (methods/classes marked @Deprecated that we still call)
   - Dead code (unused imports, unreachable branches, commented-out code blocks)
   - Copy-paste duplication (similar code blocks across files)
   - Large files/methods exceeding complexity thresholds

2. Check Brazil dependencies for:
   - Packages we consume that are marked deprecated
   - Dependencies more than 2 major versions behind latest
   - Dependencies with known security vulnerabilities
   - Homegrown solutions where standard Amazon/AWS alternatives now exist

3. Query Taskei for tech debt tracking:
   - All open tickets tagged: tech-debt, maintenance, refactor, cleanup, migration
   - Age of each ticket (how long has it been known but unaddressed)
   - Priority distribution (are they all P3/P4 and never getting done?)
   - Any with approaching deadlines (deprecation dates, compliance requirements)
   - Closed tech debt tickets in past quarter (are we making progress?)

4. Review CRUX CRs from the past 60 days for:
   - Reviewer comments saying "let's fix this later" or "track this as tech debt"
   - CRs that explicitly deferred improvements (noted in description)
   - Workarounds introduced with documented intent to fix properly later
   - Test exclusions added (skipped tests, disabled test suites)

5. Check Pipelines and build systems for:
   - Build warnings count trend (increasing = accruing debt)
   - Test coverage percentage and trend (decreasing = accruing debt)
   - Build time trend (increasing may indicate architectural issues)
   - Flaky test count (tests that pass/fail inconsistently)

6. Review oncall data for operational tech debt:
   - Recurring alerts that require manual intervention
   - Services with frequent restarts as a "fix"
   - Monitoring gaps (services with minimal observability)
   - Manual operational procedures that should be automated

7. Categorize and prioritize all identified tech debt:
   - **Safety/Security:** Vulnerabilities, deprecated crypto, auth issues
   - **Reliability:** Causes incidents, reduces availability
   - **Velocity:** Slows down development, causes merge conflicts
   - **Cost:** Inefficient resource usage, unnecessary spending
   - **Compliance:** Regulatory requirements, audit findings

## Output Format

```
## Tech Debt Inventory
**Scan Date:** [date]
**Team:** [team name]
**Packages Scanned:** [n]

---

### Summary Dashboard

| Category | Items | Trend (vs last scan) | Highest Priority Item |
|----------|-------|---------------------|----------------------|
| Safety/Security | [n] | [up/down/stable] | [item] |
| Reliability | [n] | [up/down/stable] | [item] |
| Velocity | [n] | [up/down/stable] | [item] |
| Cost | [n] | [up/down/stable] | [item] |
| Compliance | [n] | [up/down/stable] | [item] |
| **Total** | **[n]** | **[trend]** | - |

---

### Code-Level Debt

| Package | TODOs | Suppressions | Deprecated APIs | Dead Code | Complexity Violations |
|---------|-------|-------------|-----------------|-----------|----------------------|
| [name]  | [n]   | [n]         | [n]             | [n files] | [n methods]          |

**Oldest TODO:** "[text]" in [file] (added [date/CR])
**Most suppressed package:** [name] with [n] suppressions

---

### Dependency Debt

| Package | Dependency | Current | Latest | Gap | Risk |
|---------|-----------|---------|--------|-----|------|
| [pkg]   | [dep]     | [ver]   | [ver]  | [n major] | [security/deprecation/EOL] |

---

### Tracked Tech Debt (Taskei)

| Ticket | Title | Age (days) | Priority | Category | Effort Estimate |
|--------|-------|-----------|----------|----------|-----------------|
| [ID]   | [title] | [n]     | [P1-P4]  | [category] | [S/M/L/XL] |

**Total open tech debt tickets:** [n]
**Average age:** [n] days
**Oldest unaddressed:** [ticket] ([n] days old)
**Tickets closed this quarter:** [n]
**Net change this quarter:** [+/- n]

---

### Operational Debt

| Service | Issue | Impact | Frequency | Effort to Fix |
|---------|-------|--------|-----------|---------------|
| [name]  | [issue] | [what happens] | [how often] | [estimate] |

---

### Top 10 Priority Items (Recommended Sprint Allocation)

| # | Item | Category | Risk if Ignored | Effort | Suggested Owner |
|---|------|----------|-----------------|--------|-----------------|
| 1 | [item] | [cat]  | [consequence]   | [size] | [who has context] |

---

### Recommendations
1. **This sprint:** Address items #[n] (safety/reliability concerns)
2. **Next sprint:** Plan [n] story points for items #[n-n]
3. **Quarterly goal:** Reduce total inventory by [n]% (from [n] to [n] items)
4. **Process change:** [e.g., "Add tech debt review to CR checklist"]
```

## Delivery
Send the formatted report as a Slack DM to me. If any safety/security items are identified, flag them at the top of the message as requiring immediate attention. Run this report monthly to track trends.
