# Service Review Preparation

Prepare for a service review meeting: operational metrics, customer satisfaction trends, feature adoption, A/B test results, and roadmap progress.

## Data Sources
- Pipelines: deployment frequency, success rate, rollback count
- Apollo: availability, latency (p50/p90/p99), error rates, capacity utilization
- Oncall: incident count, severity, MTTR, operational load (tickets/week)
- Internal search: CSAT/NPS surveys, feature adoption dashboards, A/B test results, roadmap tracker
- Taskei: roadmap delivery vs plan, sprint velocity, blocked items
- Email/Slack: customer escalations, leadership questions from prior reviews, action items from last review
- Calendar: service review date, attendees, prior review notes

## Instructions
1. **Action items from last review.** Pull action items from the previous service review. For each: what was committed, what was delivered, what is still pending. No excuses -- status and evidence only.
2. **Operational metrics.** Present current state:
   - Availability (target vs actual, trend)
   - Latency (p50, p90, p99 -- target vs actual, trend)
   - Error rate (target vs actual, trend)
   - Deployment frequency and success rate
   - Incident count and severity distribution
   - Operational load (tickets/week, on-call burden)
3. **Customer satisfaction.** CSAT and NPS with trends. Segment by feature or workflow if data permits. Call out largest movers (positive or negative) with root cause.
4. **Feature adoption.** For features launched in the past quarter:
   - Adoption rate vs projection
   - Usage patterns (who is using it, how often, for what)
   - Customer feedback
   - Decision: invest more / maintain / deprecate
5. **A/B test results.** Active and recently concluded experiments:
   - Hypothesis, sample size, duration
   - Results with statistical significance
   - Decision (ship/iterate/kill) with justification
6. **Roadmap progress.** For each committed roadmap item:
   - Status (on track / at risk / behind / complete)
   - If at risk or behind: why, what is being done, revised ETA
7. **Risks and asks.** What does the team need from leadership? What risks need visibility?

### Amazon Writing Style Rules
- Data-driven: every metric with specific numbers, trends, and targets
- No weasel words: "making progress" must become "3 of 5 roadmap items delivered on time, 2 delayed by average of 3 weeks due to dependency on Team X"
- Customer-obsessed: frame operational metrics in customer impact terms
- "So what" for every metric: what action does it drive, what decision does it inform
- Specificity: name the feature, the metric, the date, the customer segment
- Honest about misses: present gaps with the same rigor as wins
- Prepared for questions: anticipate what leadership will ask and have the data ready

## Output Format
```
Service Review Prep - <Service Name> - <Date>

PRIOR ACTION ITEMS
| # | Action | Owner | Status | Evidence |
|---|--------|-------|--------|----------|
| 1 | ...    | ...   | ...    | ...      |

OPERATIONAL HEALTH
| Metric | Target | Actual | Trend (4 wk) | Status |
|--------|--------|--------|--------------|--------|
| Availability | ... | ... | ... | G/Y/R |
| P99 Latency  | ... | ... | ... | G/Y/R |
| Error Rate   | ... | ... | ... | G/Y/R |
| Deployment Freq | ... | ... | ... | G/Y/R |
| Incidents    | ... | ... | ... | G/Y/R |
| Ops Load     | ... | ... | ... | G/Y/R |

CUSTOMER SATISFACTION
| Metric | Score | Trend | Largest Mover | Root Cause |
|--------|-------|-------|---------------|-----------|
| CSAT   | ...   | ...   | ...           | ...       |
| NPS    | ...   | ...   | ...           | ...       |

FEATURE ADOPTION
| Feature | Launch Date | Adoption | vs Projection | Feedback | Decision |
|---------|------------|----------|---------------|----------|----------|
| ...     | ...        | ...      | ...           | ...      | ...      |

A/B TEST RESULTS
| Experiment | Hypothesis | Result | Significance | Decision |
|-----------|-----------|--------|--------------|----------|
| ...       | ...       | ...    | ...          | ...      |

ROADMAP PROGRESS
| Item | Status | ETA | Risk | Mitigation |
|------|--------|-----|------|-----------|
| ...  | ...    | ... | ...  | ...       |

RISKS AND ASKS
| # | Risk/Ask | Impact | Action Needed From |
|---|----------|--------|-------------------|
| 1 | ...      | ...    | ...               |
```

## Delivery
Send as Slack DM to the presenter 2 days before the review. Attach to the calendar invite. If prior review notes exist, include a diff of what changed.
