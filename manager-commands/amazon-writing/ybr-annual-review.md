# Annual Business Review (YBR) Narrative

Generate a Year-in-Review narrative covering full-year accomplishments, resource utilization, OKR scorecard, and next-year strategy in Amazon 6-pager format.

## Data Sources
- Pipelines: annual deployment stats, availability trend, major launches
- Apollo: year-long service health, capacity utilization
- Oncall: annual incident summary, SEV trends, operational load trajectory
- Taskei: annual velocity, delivered roadmap items vs plan
- Internal search: headcount tracker, budget actuals, OKR scorecard
- Calendar: key milestones, launches, re-orgs
- Email/Slack: leadership communications, cross-org collaborations, customer escalation trends

## Instructions
1. **Open with the customer.** Start with a narrative about how the customer's experience changed from January to December. Be specific about what improved and what remains painful.
2. **Full-year accomplishments.** Describe the 5-7 most impactful deliverables with quantified outcomes. Tie each to an OKR or org priority.
3. **Headcount utilization.** Report approved headcount vs filled positions vs effective capacity (accounting for new hire ramp, attrition, leaves). Calculate cost-per-deliverable or similar efficiency metric.
4. **Budget vs actual.** Present planned spend vs actual by category (infra, tooling, contractors, other). Explain variances greater than 10%.
5. **OKR scorecard.** For each OKR: target, actual, gap analysis, root cause for misses. Score using 0.0-1.0 scale. Aggregate team score.
6. **Lessons learned.** What mechanisms did we build this year? Which worked? What would we do differently? Be specific and actionable.
7. **Next year strategy.** Working backwards from the customer, describe the desired end state. What bets are we making? What are we choosing NOT to do? Resource implications.

### Amazon Writing Style Rules
- Data-driven: every claim backed by a metric with a specific number
- No weasel words: "significantly improved" must become "improved from X to Y (Z% gain)"
- Working backwards: start every section from the customer perspective
- Tenets as decision framework: reference tenets when explaining trade-offs
- Specificity: name systems, dates, team members, exact figures
- "So what" for every metric: what does it mean, what action does it drive
- Complete paragraphs, no bullet points in body (appendix may use tables)

## Output Format
```
[Title: 20__ Annual Business Review - <Team Name>]

Customer Impact Narrative
[1-2 paragraphs opening with customer story]

Year in Review: Accomplishments
[3-4 paragraphs covering major deliverables with metrics]

Resource Utilization
[1-2 paragraphs on headcount and budget]

OKR Scorecard
[Table in appendix, narrative summary in body]

Lessons Learned
[1-2 paragraphs on mechanisms built and gaps identified]

Next Year Strategy
[2-3 paragraphs on vision, bets, and trade-offs]

Appendix
[OKR detail table, budget breakdown, headcount timeline, key metrics dashboard]
```

## Delivery
Save as draft document. Send Slack DM with link and summary of key themes. If presenting to leadership, also prepare a 2-paragraph executive summary email.
