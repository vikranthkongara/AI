# Voice of Customer Compilation

Compile voice of customer data from multiple channels: support tickets, feedback surveys, feature requests, and pain points ranked by frequency and impact.

## Data Sources
- Internal search: support ticket system, customer feedback surveys, feature request tracker
- Email/Slack: customer escalations, account team feedback, support channel messages
- Oncall: customer-reported issues, repeat contacts for same problem
- Taskei: existing feature requests, customer-filed bugs

## Instructions
1. **Support ticket analysis.** Pull tickets from the past 2 weeks (or specified period). Categorize by:
   - Theme (what general area: onboarding, configuration, performance, access, billing)
   - Severity (blocking vs annoying vs cosmetic)
   - Frequency (how many tickets on this topic)
   - Resolution time (how long customers waited)
   Identify the top 5 themes by volume.
2. **Feedback survey synthesis.** Pull recent survey responses. Extract:
   - Verbatim quotes that illustrate key themes (positive and negative)
   - Quantitative scores by category
   - Free-text themes (cluster similar feedback)
3. **Feature requests.** Compile requested features/improvements. For each:
   - Number of unique requestors
   - Customer segment (enterprise, SMB, internal)
   - Estimated impact if built
   - Current workaround (if any)
4. **Pain points ranking.** Create a prioritized list of customer pain points ranked by: frequency (how many customers affected) x impact (how much it hurts each customer). Use a simple 2x2 matrix: high frequency + high impact = P0.
5. **Sentiment trend.** Overall: is customer sentiment improving, stable, or declining? What is driving the trend? Cite specific evidence.
6. **Emerging themes.** Any new issues appearing in the past 1-2 weeks that were not present before. Early warning signals.

### Amazon Writing Style Rules
- Customer's words first: use verbatim quotes where possible
- Data-driven: "47 tickets in 2 weeks about export timeout, up from 12 in the prior period" not "lots of complaints about exports"
- No weasel words: "customers are frustrated" must become "23 customers used words like 'broken', 'unusable', or 'unacceptable' in their feedback"
- Specificity: name the workflow, the step, the error message customers see
- "So what" for every theme: what should we build or fix based on this signal
- Customer-obsessed: present data in a way that makes the reader feel the customer's experience

## Output Format
```
Voice of Customer - <Period>

EXECUTIVE SUMMARY
[3-4 sentences: top themes, sentiment direction, urgent items]

TOP PAIN POINTS (ranked by frequency x impact)
| Rank | Pain Point | Frequency | Impact | Segment | Verbatim Quote |
|------|-----------|-----------|--------|---------|----------------|
| 1    | ...       | ...       | ...    | ...     | "..."          |

SUPPORT TICKET THEMES
| Theme | Volume | WoW Change | Avg Resolution Time | Status |
|-------|--------|------------|---------------------|--------|
| ...   | ...    | ...        | ...                 | ...    |

FEATURE REQUESTS
| Request | Requestors | Segment | Impact | Workaround | Priority |
|---------|-----------|---------|--------|------------|----------|
| ...     | ...       | ...     | ...    | ...        | ...      |

SENTIMENT TREND
[1 paragraph with evidence]

EMERGING THEMES
[New signals not previously tracked]

KEY VERBATIM QUOTES
- "[Quote 1]" - [Context]
- "[Quote 2]" - [Context]
- "[Quote 3]" - [Context]

RECOMMENDED ACTIONS
| Action | Expected Impact | Effort | Priority |
|--------|----------------|--------|----------|
| ...    | ...            | ...    | ...      |
```

## Delivery
Send as Slack DM to Service Experience Owner and product manager. Post summary (top 3 themes) to team channel. Save full report to file.
