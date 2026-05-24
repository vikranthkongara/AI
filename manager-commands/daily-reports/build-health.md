# Build Health Report

Package builder failures, flaky tests, build time trends across team packages, and overall build system health.

## Data Sources
- **Brazil Build System**: Build results for all team-owned packages
- **Pipelines**: Build stage results and durations
- **CRUX CRs**: CRs that failed build checks
- **Oncall System**: Any build infrastructure incidents

## Instructions

1. **Query build results for all team packages** (last 24 hours):
   - Total builds triggered
   - Successful vs failed vs timed out
   - Which packages had failures
   - Failure reasons (compilation error, test failure, dependency issue, infrastructure)

2. **Identify flaky tests**:
   - Tests that passed on retry without code changes
   - Tests that intermittently fail across multiple builds
   - Test suites with inconsistent results (passed in one build, failed in another for same revision)
   - Calculate flakiness rate per test suite

3. **Track build times**:
   - Average build time per package (today vs 7-day average)
   - Packages with build time increasing trend (>20% increase)
   - Longest build times and whether they are blocking developer productivity
   - Any builds that timed out

4. **Check dependency health**:
   - Build failures caused by upstream dependency updates
   - Packages pinned to old dependency versions
   - Security-flagged dependencies that need updates

5. **Identify build blockers**:
   - Packages where the main branch build is broken (trunk broken)
   - How long main branch has been broken
   - CRs that broke the build and whether a fix is in progress

6. **Infrastructure issues**:
   - Build system outages or slowdowns
   - Package builder capacity issues
   - Any systemic issues affecting multiple packages

## Output Format

```
# Build Health Report - [Date]

## Summary
- Total builds (24h): [count]
- Success rate: [%]
- Packages with failures: [count]/[total packages]
- Flaky test suites: [count]
- Avg build time: [minutes] (7-day avg: [minutes])

## Build Failures (Action Required)

### [Package Name] - BROKEN
- **Failure type**: [compilation/test/dependency/timeout]
- **Broken since**: [timestamp] ([duration])
- **Breaking CR**: [CR-xxx] by [engineer]
- **Error**: [brief error message]
- **Fix status**: [CR-yyy in progress / No fix yet / Unknown]
- **Impact**: [Blocking X other engineers / Blocking deployment]

## Flaky Tests

| Package | Test Suite | Flakiness Rate | Occurrences (7d) | Ticket |
|---------|-----------|---------------|------------------|--------|
| [pkg] | [suite] | [%] | [count] | [TASK-xxx/None] |

## Build Time Trends

| Package | Today Avg | 7-Day Avg | Trend | Concern? |
|---------|-----------|-----------|-------|----------|
| [pkg] | [min] | [min] | +[%] / -[%] | Yes/No |

## Dependency Issues
- [Package X] build failed due to [dependency] version update
- [Package Y] using deprecated version of [dependency] - update needed by [date]

## Infrastructure Notes
- [Any build system issues affecting the team]

## Recommended Actions
1. [Fix broken trunk for Package X - assign to author of breaking CR]
2. [Create ticket for flaky test in Package Y - assign to owner]
3. [Investigate build time increase in Package Z]
```

## Delivery
- Send as Slack DM to me daily at 8:30 AM
- If main branch build is broken for any package, send immediate alert
- Include links to failed build logs for quick debugging access
