# Weekly CX Pulse

Generate a weekly CX pulse report: new feedback, trending issues, resolved pain points, upcoming experiments, and customer sentiment trend.

## Data Sources
- Internal search: feedback surveys submitted this week, support ticket system, NPS responses
- Oncall: customer-facing issues this week, resolution status
- Taskei: CX items completed this week, new CX items filed
- Pipelines: CX-related deployments this week
- Email/Slack: customer feedback received, account team signals, escalations
- Apollo: error rates and latency changes that affect CX

## Instructions
1. **Headline (1 sentence).** One sentence capturing the week's CX story. Example: "Export timeout issue resolved -- 340 fewer support tickets this week, but new confusion emerging in the permissions workflow."
2. **New feedback received.** Summarize customer feedback from all channels this week:
   - Number of feedback items by channel (survey, support ticket, Slack, email)
   - Top 3 themes in this week's feedback
   - Notable verbatim quotes (positive and negative)
   - Any new issues appearing for the first time
3. **Trending issues.** Issues gaining momentum (more reports this week vs last):
   - Issue description
   - Volume this week vs last week
   - Customer impact
   - Status (investigating / fix in progress / resolved)
4. **Resolved pain points.** CX improvements shipped or issues fixed this week:
   - What was fixed
   - Customer impact (quantified where possible)
   - Confirmation that metrics improved after fix
5. **Upcoming experiments.** CX experiments launching next week:
   - Hypothesis
   - What customers will experience
   - Metrics we are watching
   - Duration and sample size
6. **Sentiment trend.** Overall direction: improving, stable, or declining. 4-week trendline with evidence.

### Amazon Writing Style Rules
- Concise: this is a pulse, not a deep dive. One sentence per item where possible.
- Data-driven: "47 tickets about X" not "several complaints about X"
- No weasel words: "sentiment is improving" must be backed by "NPS increased from 32 to 38 over 4 weeks"
- Customer-obsessed: lead with what customers are feeling and experiencing
- Actionable: every trending issue must have a status and owner
- "So what": for each data point, what should the reader do or know

## Output Format
```
Weekly CX Pulse - Week of <date>

HEADLINE: [One sentence summary of the week]

NEW FEEDBACK
- Total items: [X] (Survey: X, Support: X, Slack: X, Email: X)
- Top themes:
  1. [Theme] - [volume] - [sample quote]
  2. [Theme] - [volume] - [sample quote]
  3. [Theme] - [volume] - [sample quote]
- New signals: [Any first-time issues]

TRENDING ISSUES
| Issue | This Week | Last Week | Trend | Owner | Status |
|-------|-----------|-----------|-------|-------|--------|
| ...   | ...       | ...       | ...   | ...   | ...    |

RESOLVED THIS WEEK
| Issue | Fix Deployed | Impact | Metrics Improvement |
|-------|-------------|--------|---------------------|
| ...   | ...         | ...    | ...                 |

UPCOMING EXPERIMENTS
| Experiment | Hypothesis | Launch Date | Duration | Metrics |
|-----------|-----------|-------------|----------|---------|
| ...       | ...       | ...         | ...      | ...     |

SENTIMENT TREND
[Direction] - [4-week data points] - [Key driver]
```

## Delivery
Post to CX team Slack channel every Monday morning. Send Slack DM to product manager and engineering lead with the headline and any red items.
