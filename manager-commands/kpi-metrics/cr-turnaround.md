# CR Turnaround Metrics

Average time to first review, time to approval, and review iterations per CR, tracking reviewer responsiveness and review efficiency.

## Data Sources
- **CRUX CRs**: All code reviews with full timeline data (created, first comment, revisions, approvals, merge)
- **Calendar**: Working hours and PTO to calculate business-hours metrics
- **Taskei**: Linked tickets to understand priority of changes being reviewed

## Instructions

1. **Pull all CRs from the measurement period** (default: last 30 days):
   - Creation timestamp
   - Each revision timestamp
   - Each reviewer comment timestamp
   - Approval timestamps (per reviewer)
   - Merge timestamp
   - Lines changed, files changed

2. **Calculate time-to-first-review**:
   - Time from CR creation to first substantive reviewer comment
   - Per reviewer (who responds fastest)
   - By time of day created (do morning CRs get reviewed faster?)
   - By CR size (do small CRs get reviewed faster?)
   - Business hours only vs wall clock time

3. **Calculate time-to-approval**:
   - Time from CR creation to first approval
   - Time from CR creation to all required approvals
   - Time from last revision to next reviewer response
   - Per reviewer average response time

4. **Calculate review iterations**:
   - Average number of revision rounds per CR
   - CRs that merged on first revision vs required rework
   - Correlation between iterations and CR size
   - Correlation between iterations and author experience

5. **Reviewer efficiency metrics**:
   - Reviews completed per reviewer per week
   - Average response time per reviewer
   - Review depth (comments per review, types of comments)
   - Reviewer availability patterns (fast on which days/times)

6. **Identify bottlenecks**:
   - CRs waiting longest for review
   - Reviewers with highest response times
   - Times of day/week when reviews are slowest
   - External reviewers vs internal response time difference

## Output Format

```
# CR Turnaround Report - [Period: Start Date to End Date]

## Team Summary
- CRs created: [count] | CRs merged: [count]
- Avg time to first review: [hours]
- Avg time to approval: [hours]
- Avg review iterations: [X]
- Trend: [improving/stable/declining]

## Key Metrics

| Metric | Average | Median | P90 | Target | Status |
|--------|---------|--------|-----|--------|--------|
| Time to first review | [hrs] | [hrs] | [hrs] | <4h | [met/not met] |
| Time to approval | [hrs] | [hrs] | [hrs] | <24h | [met/not met] |
| Review iterations | [X] | [X] | [X] | <3 | [met/not met] |
| Approval to merge | [hrs] | [hrs] | [hrs] | <2h | [met/not met] |

## Per-Reviewer Response Times

| Reviewer | Reviews Done | Avg First Response | Avg to Approval | Trend |
|----------|-------------|-------------------|-----------------|-------|
| [name] | [count] | [hours] | [hours] | [arrow] |

## Per-Author Metrics

| Author | CRs Created | Avg Iterations | First-Pass Approval % | Avg Size |
|--------|-------------|----------------|----------------------|----------|
| [name] | [count] | [X] | [%] | [lines] |

## By CR Size

| Size | Count | Avg First Review | Avg Approval | Avg Iterations |
|------|-------|-----------------|-------------|----------------|
| Small (<50) | [count] | [hrs] | [hrs] | [X] |
| Medium (50-200) | [count] | [hrs] | [hrs] | [X] |
| Large (200+) | [count] | [hrs] | [hrs] | [X] |

## Review Iteration Analysis
- First-pass approval rate: [X]%
- Most common feedback themes: [list]
- CRs with 4+ iterations: [count] (investigate for coaching opportunities)

## Weekly Trend

| Week | First Review | Approval | Iterations | CRs Merged |
|------|-------------|----------|-----------|-----------|
| [date] | [hrs] | [hrs] | [X] | [count] |

## Bottlenecks Identified
- [Reviewer X] avg response [Y] hours - above team average
- CRs created after 4 PM wait [X] hours longer on average
- External reviews from [Team Z] average [X] hours response time

## Recommendations
- [Set team SLA: first review within 4 business hours]
- [Pair [slow reviewer] with [fast reviewer] to balance load]
- [Author [name] may benefit from design discussion before CR to reduce iterations]
```

## Delivery
- Send as Slack DM to me every Monday morning
- Include per-engineer breakdown for 1:1 preparation
- Flag if any CR has been waiting for first review for more than 24 business hours
