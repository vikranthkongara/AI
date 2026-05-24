# Quarterly Business Review (QBR) Narrative

Generate a 6-page QBR narrative for the current quarter, formatted in Amazon's narrative writing style with no bullet points in the body text.

## Data Sources
- Pipelines: deployment frequency, success rate, rollback count for the quarter
- Apollo: service health metrics, availability, latency percentiles (p50, p90, p99)
- Oncall: incident count, severity breakdown, MTTR, pages per week trend
- Taskei: sprint velocity, delivered vs committed, blocked items
- Internal search: org-level OKR tracker, headcount dashboard
- Calendar: key milestones delivered this quarter
- Email/Slack: customer escalations, leadership asks, cross-team dependencies

## Instructions
1. **Open with a customer anecdote.** Find a real customer interaction (support ticket, feedback, or escalation) that illustrates the quarter's theme. Make it specific: name the workflow, the friction, the outcome.
2. **State of the business.** Present 5-8 key metrics with Year-over-Year (YoY) and Quarter-over-Quarter (QoQ) comparisons. For every metric, answer "so what" -- what does this number mean for the customer and what action does it drive.
3. **What worked.** Describe 2-3 initiatives that delivered measurable results. Be specific: "Reduced p99 latency from 1200ms to 340ms by implementing connection pooling" not "improved performance significantly."
4. **What didn't work.** Be candid. Describe 1-2 misses with root cause analysis. No blame, focus on mechanism gaps. What will we change.
5. **Key initiatives next quarter.** List 3-5 priorities with expected customer impact, success metrics, owners, and dependencies.
6. **Tenets invoked.** Reference team tenets where they guided decisions this quarter.

### Amazon Writing Style Rules
- Every claim must be backed by a specific metric or data point
- No weasel words: ban "significantly", "various", "some", "greatly", "many"
- Write in complete paragraphs, not bullet points (appendix may use tables)
- Start every section by grounding in customer impact
- "So what" test: if a metric does not drive an insight or action, remove it
- Be specific: dates, numbers, names of systems, percentages with denominators
- Use tenets as a decision-making framework, not decoration

## Output Format
```
[Title: Q_ 20__ Business Review - <Team Name>]

[Opening customer anecdote - 1 paragraph]

State of the Business
[2-3 paragraphs with inline metrics, YoY/QoQ comparisons]

What Worked
[2-3 paragraphs, one per initiative]

What Didn't Work
[1-2 paragraphs with root cause and corrective mechanisms]

Key Initiatives Next Quarter
[2-3 paragraphs describing priorities and expected outcomes]

Appendix
[Metrics table, dependency tracker, headcount summary]
```

## Delivery
Save as a draft document and send a Slack DM with the link. If an email distribution list is specified, send as email attachment in PDF-ready format.
