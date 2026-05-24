# Service Experience Owner Metrics Dashboard

Generate a CX metrics dashboard for the Service Experience Owner covering satisfaction scores, task completion rates, error rates, time-on-task, and funnel analysis.

## Data Sources
- Internal search: CSAT/NPS survey results, task completion analytics, funnel data
- Apollo: service error rates by API endpoint, latency by workflow
- Oncall: customer-facing errors, degraded experience incidents
- Pipelines: recent deployments that may affect CX metrics
- Email/Slack: customer feedback, support ticket trends, escalations
- Taskei: CX improvement initiatives in progress

## Instructions
1. **Satisfaction scores.** Pull latest CSAT and NPS scores. Show trend over 4 weeks and 3 months. Segment by workflow or feature if data permits. For any score that dropped more than 5 points, investigate root cause.
2. **Task completion rates.** For each key customer workflow: what percentage of customers who start the workflow complete it successfully? Compare to prior period. Identify the specific step where drop-off is highest.
3. **Error rates by workflow.** Break down customer-visible errors by workflow: which flows have the highest error rate? What errors do customers see (4xx vs 5xx, validation errors, timeouts)? Quantify customer impact.
4. **Time-on-task.** For each key workflow: median and p90 time to complete. Compare to target. Identify workflows where time-on-task has increased (regression) or decreased (improvement).
5. **Drop-off funnel analysis.** For the primary customer journey: show conversion at each step. Identify the largest drop-off points. Hypothesize why customers are abandoning and what data would confirm.
6. **Week-over-week trend.** For all metrics, show WoW change and flag any that moved more than 10%.
7. **Action items.** For each metric in yellow/red status: what is being done, who owns it, when is it expected to resolve.

### Amazon Writing Style Rules
- Data-driven: "Task completion dropped from 87% to 79% in the payment flow at the address validation step" not "completion rates went down"
- No weasel words: "some customers are having issues" must become "342 customers (4.2% of daily active) encountered timeout errors in the export workflow"
- Customer-obsessed: frame every metric in terms of customer pain or delight
- "So what" for every number: what action does this metric drive
- Specificity: name the workflow, the step, the error, the customer segment

## Output Format
```
CX Dashboard - <Service/Product Name> - Week of <date>

SATISFACTION
| Metric | This Week | Last Week | WoW | 4-Week Trend | 3-Month Trend | Status |
|--------|-----------|-----------|-----|--------------|---------------|--------|
| CSAT   | ...       | ...       | ... | ...          | ...           | G/Y/R  |
| NPS    | ...       | ...       | ... | ...          | ...           | G/Y/R  |

TASK COMPLETION
| Workflow | Completion Rate | WoW | Drop-off Step | Status |
|----------|----------------|-----|---------------|--------|
| ...      | ...            | ... | ...           | G/Y/R  |

ERROR RATES
| Workflow | Error Rate | WoW | Top Error | Customers Affected | Status |
|----------|-----------|-----|-----------|-------------------|--------|
| ...      | ...       | ... | ...       | ...               | G/Y/R  |

TIME ON TASK
| Workflow | Median | P90 | Target | WoW | Status |
|----------|--------|-----|--------|-----|--------|
| ...      | ...    | ... | ...    | ... | G/Y/R  |

FUNNEL
| Step | Entry | Exit | Conversion | Drop-off | Status |
|------|-------|------|------------|----------|--------|
| ...  | ...   | ...  | ...        | ...      | G/Y/R  |

ACTION ITEMS
| Metric | Issue | Owner | Action | ETA |
|--------|-------|-------|--------|-----|
| ...    | ...   | ...   | ...    | ... |
```

## Delivery
Post to CX team Slack channel. Send Slack DM to Service Experience Owner with summary of red/yellow items. Save to file for historical tracking.
