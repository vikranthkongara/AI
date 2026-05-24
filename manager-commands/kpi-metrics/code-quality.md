# Code Quality Metrics

Static analysis trends, test coverage changes, linting violations introduced vs fixed, and overall code health indicators.

## Data Sources
- **Brazil Build System**: Static analysis reports, test coverage data, linting results
- **CRUX CRs**: Per-CR quality metrics (test additions, coverage impact)
- **Pipelines**: Quality gate results in CI/CD
- **Taskei**: Tech debt and code quality tickets

## Instructions

1. **Pull static analysis data** for all team packages:
   - Total findings by severity (critical, high, medium, low)
   - New findings introduced in the last period
   - Findings resolved/fixed in the last period
   - Net change (are we improving or declining?)
   - Findings by category (security, performance, correctness, style)

2. **Track test coverage**:
   - Current coverage percentage per package
   - Coverage change over last 30 days
   - CRs that decreased coverage (no tests added for new code)
   - CRs that increased coverage (tests added for existing code)
   - Branch coverage vs line coverage

3. **Monitor linting and style**:
   - Linting violations per package
   - New violations introduced per CR
   - Violations fixed per CR
   - Top recurring violation types

4. **Assess test health**:
   - Total test count per package
   - Tests added vs tests removed over time
   - Test execution time trends
   - Flaky test count and trend
   - Test-to-code ratio

5. **Track tech debt indicators**:
   - Complexity metrics (cyclomatic complexity trends)
   - Code duplication percentage
   - Deprecated API usage
   - TODO/FIXME count trends
   - Age of oldest unaddressed tech debt tickets

6. **Per-engineer code quality**:
   - Coverage contribution (tests added per CR)
   - Static analysis findings introduced per engineer
   - Code review feedback patterns (quality-related comments received)

## Output Format

```
# Code Quality Report - [Period: Start Date to End Date]

## Summary
- Overall code health: [Improving/Stable/Declining]
- Avg test coverage: [X]% (target: [Y]%)
- Static analysis findings: [X] open ([+/-Y] vs last period)
- Linting violations: [X] open ([+/-Y] vs last period)
- Flaky tests: [X] (target: 0)

## Test Coverage

| Package | Current | 30d Change | Target | Status |
|---------|---------|-----------|--------|--------|
| [pkg] | [%] | [+/-%] | [%] | [Met/Below] |

## Coverage Trends (Last 8 Weeks)
- Week 1: [%] | Week 2: [%] | ... | Week 8: [%]
- Direction: [improving/stable/declining]
- CRs without tests this period: [count] ([%] of total CRs)

## Static Analysis

| Severity | Open | New (Period) | Fixed (Period) | Net Change |
|----------|------|-------------|----------------|-----------|
| Critical | [count] | [count] | [count] | [+/-] |
| High | [count] | [count] | [count] | [+/-] |
| Medium | [count] | [count] | [count] | [+/-] |
| Low | [count] | [count] | [count] | [+/-] |

## Top Finding Categories

| Category | Count | Trend | Example |
|----------|-------|-------|---------|
| [category] | [count] | [arrow] | [brief example] |

## Linting Health

| Package | Violations | New | Fixed | Net | Trend |
|---------|-----------|-----|-------|-----|-------|
| [pkg] | [count] | [count] | [count] | [+/-] | [arrow] |

## Per-Engineer Quality Contributions

| Engineer | CRs | Avg Coverage Impact | Tests Added | Findings Introduced |
|----------|-----|--------------------:|------------|-------------------|
| [name] | [count] | [+/-%] | [count] | [count] |

## Tech Debt Indicators

| Metric | Current | Previous | Trend | Concern? |
|--------|---------|----------|-------|----------|
| Avg complexity | [X] | [X] | [arrow] | [Yes/No] |
| Code duplication | [%] | [%] | [arrow] | [Yes/No] |
| Deprecated APIs | [count] | [count] | [arrow] | [Yes/No] |
| TODO/FIXME count | [count] | [count] | [arrow] | [Yes/No] |

## Flaky Tests

| Package | Test | Flakiness Rate | Open Since | Ticket |
|---------|------|---------------|-----------|--------|
| [pkg] | [test name] | [%] | [date] | [TASK-xxx] |

## Recommendations
1. [Address critical static analysis findings in [package]]
2. [Improve coverage for [package] - currently below target]
3. [Fix or quarantine [X] flaky tests]
4. [Engineer [name] - discuss testing practices (multiple CRs without tests)]
5. [Schedule tech debt sprint to address [category] findings]
```

## Delivery
- Send as Slack DM to me every Monday morning
- Detailed monthly report on first Monday of each month
- Alert if test coverage drops below team threshold (e.g., 80%)
- Alert if critical static analysis findings are introduced
