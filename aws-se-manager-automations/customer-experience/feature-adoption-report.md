# Feature Adoption Report

Track feature adoption: launch date, adoption curve, usage by segment, feedback, comparison to projections, and invest/maintain/deprecate recommendation.

## Data Sources
- Internal search: feature usage analytics, adoption dashboards, launch projections
- Taskei: feature launch tickets, follow-up work items
- Pipelines: deployment dates, feature flag status
- Email/Slack: customer feedback about the feature, account team reports
- Apollo: performance metrics for the feature (latency, errors specific to this feature)
- Oncall: issues related to the feature

## Instructions
1. **Feature overview.** For each feature being tracked:
   - Name and brief description (1 sentence)
   - Launch date and rollout status (% of customers with access)
   - Original hypothesis: what customer problem does it solve
   - Original projection: expected adoption at 30/60/90 days
2. **Adoption metrics.** For each feature:
   - Total users who have tried the feature (ever)
   - Active users (used in past 7 days)
   - Adoption rate: active users / eligible users
   - Adoption curve: daily/weekly adoption over time
   - Comparison to projection: ahead/behind by how much
3. **Usage patterns.** How customers are using the feature:
   - Frequency (daily, weekly, monthly)
   - Depth (using basic vs advanced capabilities)
   - Session duration with the feature
   - Common workflows involving the feature
4. **Segmentation.** Adoption broken down by:
   - Customer segment (enterprise, SMB, individual)
   - Geography (if relevant)
   - Account age (new vs established customers)
   - Usage tier (light vs heavy users)
5. **Customer feedback.** Qualitative signals:
   - Positive feedback (quotes, themes)
   - Negative feedback (quotes, themes)
   - Feature requests (what's missing)
   - Support tickets related to the feature
6. **Performance health.** Operational metrics specific to this feature:
   - Error rate
   - Latency
   - Any reliability concerns
7. **Recommendation.** Based on all data, recommend one of:
   - **Invest:** Adoption exceeds projections, feedback is positive, expand and enhance
   - **Maintain:** Adoption meets projections, no major issues, continue as-is
   - **Iterate:** Adoption below projections but feedback suggests fixable issues
   - **Deprecate:** Low adoption, negative feedback, high operational cost -- consider sunsetting
   Support recommendation with specific evidence.

### Amazon Writing Style Rules
- Data-driven: "412 of 3,200 eligible customers adopted within 30 days (12.9%, vs 20% projection)" not "adoption is lower than expected"
- No weasel words: "growing well" must become "week-over-week growth of 8.3% for 4 consecutive weeks"
- Customer-obsessed: explain adoption through the lens of customer value
- "So what": every metric must drive a decision (invest/maintain/iterate/deprecate)
- Specificity: name the feature, the segment, the exact numbers
- Honest about misses: if adoption is low, explore why without making excuses

## Output Format
```
Feature Adoption Report - <Date>

PORTFOLIO SUMMARY
| Feature | Launch | Adoption Rate | vs Projection | Trend | Recommendation |
|---------|--------|--------------|---------------|-------|----------------|
| ...     | ...    | ...          | ...           | ...   | ...            |

DETAILED ANALYSIS

[Feature 1: <Name>]
- Hypothesis: [Customer problem it solves]
- Launch: [Date] | Rollout: [X% of customers]
- Adoption: [X users / Y eligible = Z%]
- Projection comparison: [Ahead/Behind by X%]
- Usage: [Frequency, depth, duration]
- Segments:
  | Segment | Adoption | Trend |
  |---------|----------|-------|
  | ...     | ...      | ...   |
- Feedback: [Top positive theme] | [Top negative theme]
- Health: Error rate [X%], Latency [Xms]
- Recommendation: [Invest/Maintain/Iterate/Deprecate]
- Evidence: [Why this recommendation]
- Next steps: [Specific actions]

[Repeat for each feature]

ADOPTION TRENDS (4-week view)
| Feature | Week 1 | Week 2 | Week 3 | Week 4 | Direction |
|---------|--------|--------|--------|--------|-----------|
| ...     | ...    | ...    | ...    | ...    | ...       |

DECISIONS NEEDED
| Feature | Question | Data Available | Deadline |
|---------|----------|---------------|----------|
| ...     | ...      | ...           | ...      |
```

## Delivery
Send as Slack DM to product manager and engineering lead. Post summary table to team channel. If any feature is recommended for deprecation, flag for leadership discussion.
