# Headcount Tracking

Track headcount plan versus actual: approved roles, filled positions, pending hires, time-to-fill metrics, and budget utilization.

## Data Sources
- Email/Outlook (headcount approval communications, offer letters, start dates)
- Taskei (headcount tracking tasks, role status)
- Calendar (new hire start dates, onboarding sessions)
- Slack DMs (recruiter updates, hiring manager discussions)

## Instructions
1. Query Taskei and email for the current headcount plan. For each approved position, determine:
   - Role title, level, and team/sub-team
   - Approval date
   - Current status (Open/Sourcing, Interviewing, Offer Extended, Offer Accepted, Filled, On Hold, Cancelled)
   - Target fill date (from original plan)
   - Actual or projected fill date
   - Recruiter assigned
2. Calculate headcount metrics:
   - Total approved headcount for the period
   - Positions filled (candidate started)
   - Positions with accepted offers (pending start)
   - Positions actively being filled
   - Positions on hold or cancelled
   - Remaining gap (approved minus filled/accepted)
3. Calculate time-to-fill for each completed hire:
   - Days from role approval to posting
   - Days from posting to first qualified candidate
   - Days from first candidate to offer
   - Days from offer to acceptance
   - Days from acceptance to start date
   - Total end-to-end time
4. Compare against benchmarks:
   - Team historical average time-to-fill
   - Organization-level benchmarks by level
   - Industry benchmarks for the role type
5. Identify risks and blockers:
   - Roles that have exceeded target fill date
   - Roles with no pipeline activity
   - Roles where headcount approval may expire
   - Budget constraints affecting pending offers
6. Track attrition impact:
   - Departures this period (backfill needed)
   - Net headcount change (hires minus departures)
   - Backfill positions vs new growth positions
7. Project future state:
   - Expected team size at end of quarter (based on accepted offers and projected fills)
   - Budget burn rate and remaining hiring budget
8. Check email for any communications about headcount freezes, reorgs, or plan changes.

## Output Format
```
## Headcount Tracking Report
**Date:** [Date]
**Period:** [Quarter/Half]
**Current Team Size:** [N]
**Target Team Size:** [N]
**Gap:** [N] positions

### Executive Summary
| Metric | Count |
|--------|-------|
| Approved headcount (period) | [N] |
| Filled (started) | [N] |
| Offer accepted (pending start) | [N] |
| Actively recruiting | [N] |
| On hold | [N] |
| Cancelled | [N] |
| Net gap to plan | [N] |

### Headcount Plan Detail
| Role | Level | Status | Opened | Target Fill | Projected Fill | Days Open | Recruiter |
|------|-------|--------|--------|-------------|----------------|-----------|-----------|
| [Title] | [L4-7] | [Status] | [Date] | [Date] | [Date] | [N] | [Name] |

### Time-to-Fill Metrics
| Metric | Current Avg | Target | Best | Worst | Benchmark |
|--------|-------------|--------|------|-------|-----------|
| Approval to posting | [X days] | [Y] | [Z] | [W] | [B] |
| Posting to first candidate | [X days] | [Y] | [Z] | [W] | [B] |
| First candidate to offer | [X days] | [Y] | [Z] | [W] | [B] |
| Offer to acceptance | [X days] | [Y] | [Z] | [W] | [B] |
| Acceptance to start | [X days] | [Y] | [Z] | [W] | [B] |
| **Total end-to-end** | [X days] | [Y] | [Z] | [W] | [B] |

### Time-to-Fill by Level
| Level | Avg Days | Count Filled | Trend |
|-------|----------|-------------|-------|
| L4 | [X] | [N] | [Arrow] |
| L5 | [X] | [N] | [Arrow] |
| L6 | [X] | [N] | [Arrow] |
| L7+ | [X] | [N] | [Arrow] |

### At-Risk Positions
| Role | Risk Factor | Days Over Target | Impact | Recommended Action |
|------|-------------|-----------------|--------|-------------------|
| [Role] | No pipeline | [N] days | [Delivery impact] | [Escalate with recruiter] |
| [Role] | Offer declined | [N] days | [Delivery impact] | [Re-source immediately] |

### Attrition & Net Change
| Metric | This Quarter | Last Quarter | YTD |
|--------|-------------|--------------|-----|
| Departures | [N] | [N] | [N] |
| New hires started | [N] | [N] | [N] |
| Net change | [+/-N] | [+/-N] | [+/-N] |
| Backfill positions | [N] | [N] | [N] |
| Growth positions | [N] | [N] | [N] |

### Upcoming Start Dates
| Name | Role | Start Date | Onboarding Plan | Buddy Assigned |
|------|------|-----------|-----------------|----------------|

### Budget Status
| Category | Budgeted | Used | Remaining | Projected EOQ |
|----------|----------|------|-----------|---------------|
| Headcount slots | [N] | [N] | [N] | [N] |
| Comp budget | [X] | [Y] | [Z] | [W] |

### Projected Team Size
| Date | Projected Size | Confidence | Assumptions |
|------|---------------|------------|-------------|
| End of month | [N] | [H/M/L] | [Pending starts] |
| End of quarter | [N] | [H/M/L] | [Based on pipeline] |

### Recommendations
1. [Action for stalled positions]
2. [Action for budget optimization]
3. [Action for reducing time-to-fill]
```

## Delivery
Send the full report as a Slack DM to me on the 1st and 15th of each month. Send immediate alerts if a headcount freeze is communicated, an offer is declined, or a team member gives notice (triggering backfill need).
