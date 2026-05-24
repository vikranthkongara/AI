# Weekly Business Review (WBR) Metrics Report

Generate a WBR metrics report with input/output metrics, Week-over-Week trends, and 4-week trendlines with RAG status indicators.

## Data Sources
- Pipelines: deployment count, success/failure rate, rollback count
- Apollo: service availability, latency (p50, p90, p99), error rates by API
- Oncall: tickets created, pages received, MTTR, severity breakdown
- Taskei: stories completed, sprint burndown, blocked items count
- Internal search: WAR (weekly active rate), DAU, feature usage counters
- CRs: code reviews opened, approved, time-to-merge
- Slack/Email: customer-reported issues this week

## Instructions
1. **Collect metrics** from all data sources for the current week and previous 4 weeks.
2. **Classify as input or output metrics.**
   - Input metrics: things we control (deployment frequency, code review throughput, sprint velocity, operational tickets addressed)
   - Output metrics: results we measure (availability, latency, error rate, WAR, customer satisfaction)
3. **Calculate Week-over-Week (WoW) delta** for each metric. Express as absolute change and percentage.
4. **Assign RAG status:**
   - Green: metric at or better than target, positive trend
   - Yellow: metric within 10% of target or trending in wrong direction for 2+ weeks
   - Red: metric missed target or trending wrong for 3+ weeks
5. **Add 4-week sparkline trend** description (improving, stable, degrading).
6. **Write "so what" commentary** for any Yellow or Red metric: what caused it, what action is being taken, expected recovery date.
7. **Highlight anomalies.** Call out any metric that moved more than 20% WoW with explanation.

### Amazon Writing Style Rules
- No weasel words: replace "some increase" with "14% increase from 230 to 262"
- Every red/yellow metric must have an owner and action
- Metrics without context are noise -- always pair with "so what"
- Be specific about denominators: "99.2% availability (43,200 requests, 346 errors)" not just "99.2%"

## Output Format
```
WBR - <Team Name> - Week of <date>

INPUT METRICS
| Metric | This Week | Last Week | WoW Delta | 4-Week Trend | Target | Status |
|--------|-----------|-----------|-----------|--------------|--------|--------|
| ...    | ...       | ...       | ...       | ...          | ...    | G/Y/R  |

OUTPUT METRICS
| Metric | This Week | Last Week | WoW Delta | 4-Week Trend | Target | Status |
|--------|-----------|-----------|-----------|--------------|--------|--------|
| ...    | ...       | ...       | ...       | ...          | ...    | G/Y/R  |

COMMENTARY
[Yellow/Red items with root cause, owner, action, expected resolution]

HIGHLIGHTS
[Anomalies, wins worth calling out, risks emerging]
```

## Delivery
Post to the team's WBR Slack channel. If a specific recipient is named, also send as Slack DM. Save to file for historical tracking.
