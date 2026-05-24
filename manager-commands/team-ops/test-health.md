# Test Health Report

Identify flaky tests, test coverage gaps, slow tests degrading CI time, and overall test suite health. Poor test health directly impacts team velocity through wasted time on false failures and reduced confidence in deployments.

## Data Sources
- Pipelines: build history, test execution results, CI duration trends
- Brazil Build System: test coverage reports, package test configurations
- CRUX CRs: test changes, skipped tests added, test-related comments
- Taskei: flaky test tickets, test infrastructure tasks
- Oncall system: deployment failures caused by test issues

## Instructions

1. Analyze test execution history from Pipelines (past 30 days):
   - Total test suite pass rate (excluding known flaky tests)
   - Number of distinct tests that have flaked (passed and failed on same code)
   - Frequency of each flaky test (how often does it fail?)
   - False failure rate (builds that failed on tests but passed on retry)
   - Time wasted on flaky tests (retries x build time)

2. Identify the top flaky tests:
   - Sort by failure frequency
   - Note which package/service they belong to
   - Identify when they became flaky (correlate with CRs)
   - Check if there are existing Taskei tickets to fix them
   - Calculate the "cost" of each (retries triggered, developer time wasted)

3. Test coverage analysis from Brazil builds:
   - Overall test coverage percentage per package
   - Coverage trend (increasing or decreasing over past 3 months)
   - Files/modules with zero coverage
   - Recently changed code without corresponding test changes (CRUX CRs with no test files modified)
   - Critical paths (business logic, error handling) with low coverage

4. CI performance analysis:
   - Average build + test time (overall and per package)
   - Test time as percentage of total CI duration
   - Slowest tests (top 10 by execution time)
   - Test time trend (getting faster or slower?)
   - Parallelization opportunities (tests that could run concurrently)

5. Test quality signals:
   - Tests recently skipped/disabled (from CRUX CRs with @Ignore, @Skip, @Disabled)
   - Tests with no assertions (exist but don't verify anything)
   - Integration tests without proper cleanup (resource leaks)
   - Tests depending on external services without mocks (fragile)
   - Test data hardcoded with production values (security risk)

6. Deployment impact:
   - Deployments delayed by test failures in past 30 days
   - Production incidents that existing tests should have caught
   - Test environments with different configurations than production

## Output Format

```
## Test Health Report
**Period:** Past 30 days
**Team:** [team name]
**Overall Pass Rate:** [%] (target: > 99%)
**Flaky Test Count:** [n] (target: 0)
**Average CI Time:** [minutes] (trend: [faster/slower] by [%])

---

### Health Summary

| Metric | Current | Target | Status | Trend |
|--------|---------|--------|--------|-------|
| Pass rate | [%] | > 99% | [G/Y/R] | [trend] |
| Flaky tests | [n] | 0 | [G/Y/R] | [trend] |
| Coverage | [%] | > 80% | [G/Y/R] | [trend] |
| CI duration | [min] | < [target] min | [G/Y/R] | [trend] |
| Skipped tests | [n] | 0 | [G/Y/R] | [trend] |

---

### Top Flaky Tests (Fix These First)

| # | Test Name | Package | Failure Rate | Flaky Since | Cost (retries) | Ticket |
|---|-----------|---------|-------------|-------------|----------------|--------|
| 1 | [test]    | [pkg]   | [%]         | [date]      | [n retries]    | [ID or "none"] |
| 2 | [test]    | [pkg]   | [%]         | [date]      | [n retries]    | [ID or "none"] |

**Total time wasted on flaky tests this month:** ~[n] hours of CI time, ~[n] hours of developer time

---

### Coverage Gaps

| Package | Coverage | Delta (30d) | Critical Uncovered Areas |
|---------|----------|-------------|--------------------------|
| [pkg]   | [%]      | [+/-%]      | [e.g., "error handling in PaymentProcessor"] |

**Files with 0% coverage that have been modified recently:**
- [file path] (modified [date], [n] lines, no tests)
- [file path] (modified [date], [n] lines, no tests)

---

### Slow Tests (CI Bottlenecks)

| # | Test | Package | Duration | Type | Optimization |
|---|------|---------|----------|------|-------------|
| 1 | [test] | [pkg] | [seconds] | [unit/integration] | [suggestion] |

**If top 5 slow tests were optimized, CI would be [n] minutes faster ([%] improvement)**

---

### Recently Disabled Tests

| Test | Package | Disabled By | Date | Reason | Ticket to Re-enable |
|------|---------|-------------|------|--------|---------------------|
| [test] | [pkg] | [engineer] | [date] | [reason from CR] | [ID or "none - create one"] |

---

### Tests vs Code Changes (Coverage Discipline)

- CRs with code changes and corresponding tests: [n] ([%])
- CRs with code changes but NO test changes: [n] ([%])
- Notable gaps: [list CRs that changed critical logic without tests]

---

### Recommendations
1. **This sprint:** Fix top [n] flaky tests (saves ~[n] hours/month of CI time)
2. **This sprint:** Add tests for [critical uncovered areas]
3. **Next sprint:** Optimize [slowest tests] to reduce CI by [n] minutes
4. **Process:** [e.g., "Require test coverage for all CRs touching business logic"]
5. **Infrastructure:** [e.g., "Investigate test parallelization for [package]"]
```

## Delivery
Send the formatted report as a Slack DM to me. If flaky test count exceeds 5 or CI time has increased by more than 25% month-over-month, flag as requiring team discussion in next sprint planning. Include links to specific flaky tests so we can assign them during the meeting.
