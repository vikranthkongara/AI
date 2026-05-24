# OP1 Planning Document

Generate an OP1 (annual planning) document in Amazon 6-pager narrative format: vision, current state, future state, resource asks, and execution plan.

## Data Sources
- Internal search: org strategy docs, VP-level goals, prior year OP1/OP2 documents
- Taskei: current backlog, tech debt items, deferred roadmap items
- Pipelines/Apollo: current operational baseline (availability, latency, deployment cadence)
- Oncall: operational load trends, incident patterns indicating investment needs
- Email/Slack: leadership guidance on priorities, cross-team dependency requests
- Calendar: planning deadlines, review dates

## Instructions
1. **Vision (1 paragraph).** Describe the 3-year customer end state. What does the world look like if we succeed? Be specific about the customer experience, not internal mechanics.
2. **Tenets (5-7 tenets).** Decision-making principles for the year. Each tenet should resolve a real tension (e.g., "We prioritize reliability over feature velocity when availability drops below 99.9%"). Include "especially when" clause.
3. **Current state.** Honest assessment of where we are: strengths, weaknesses, technical debt, organizational gaps. Back with data.
4. **Future state.** Where we need to be by end of next year. Describe in customer-observable terms. Define 3-5 measurable outcomes.
5. **Gap analysis.** What must change to get from current to future state? Categorize: people, process, technology.
6. **Resource asks.** Headcount (by role and level), infrastructure budget, tooling investments. Justify each ask with expected ROI or risk if not funded.
7. **Dependencies.** What do we need from other teams? What are other teams expecting from us? Name the teams, the deliverables, the dates.
8. **Risks.** Top 5 risks with likelihood, impact, and mitigation plan.
9. **Timeline.** Quarter-by-quarter milestones for the year.

### Amazon Writing Style Rules
- Data-driven: ground every assertion in current metrics or historical trends
- No weasel words: "We need more engineers" must become "We need 3 SDE IIs to deliver the caching tier by Q2, which will reduce p99 latency from 800ms to 200ms"
- Customer-obsessed: every ask tied back to customer impact
- Tenets as decision framework: show how tenets resolve real trade-offs
- Specificity: exact headcount, exact dollar amounts, exact dates
- "So what" for every investment: what customer outcome does it unlock

## Output Format
```
[Title: OP1 20__ - <Team Name>]

Vision
[1 paragraph, 3-year customer end state]

Tenets
[5-7 tenets with "especially when" clauses]

Current State
[2-3 paragraphs with data]

Future State
[1-2 paragraphs, customer-observable outcomes]

Gap Analysis
[1-2 paragraphs categorized by people/process/technology]

Resource Asks
[1-2 paragraphs in body, detail table in appendix]

Dependencies
[1 paragraph with named teams and deliverables]

Risks
[1 paragraph summary, detail table in appendix]

Timeline
[1 paragraph summary, Gantt-style table in appendix]

Appendix
[Headcount table, budget breakdown, dependency matrix, risk register, timeline]
```

## Delivery
Save as draft document. Send Slack DM with link. Flag any sections where data is incomplete and list what additional inputs are needed.
