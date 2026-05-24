# Six-Pager Narrative

Generate a full 6-page narrative document in Amazon's canonical format: complete paragraphs, no bullet points in the body, data-rich, customer-obsessed.

## Data Sources
- Internal search: prior art, competitive landscape, org strategy, related proposals
- Taskei: customer requests, backlog context, effort estimates
- Pipelines/Apollo: operational metrics, system constraints, capacity data
- Oncall: incident history, operational burden data
- Email/Slack: stakeholder input, customer feedback, leadership direction
- CRs: technical context for proposed changes
- Calendar: relevant review dates, deadlines

## Instructions
1. **Customer obsession opener (1 paragraph).** Begin with a specific, vivid customer story that embodies the problem. Not hypothetical -- use real data, real workflows, real pain points. The reader should feel the customer's frustration.
2. **Context (1-2 paragraphs).** Set the stage: what is the current state, how did we get here, what has changed that makes this proposal timely now. Ground in facts and metrics.
3. **Problem (2-3 paragraphs).** Define the problem precisely. Quantify its impact: cost, frequency, customer harm, opportunity cost. Explain why existing solutions are insufficient.
4. **Tenets (5-7 tenets).** Decision-making principles for this initiative. Each should resolve a real tension with an "especially when" clause. These are not aspirational values -- they are practical tools for making trade-offs.
5. **Proposed solution (3-4 paragraphs).** Describe the solution in enough detail that a reader understands what will be built, how it works from the customer's perspective, and why this approach was chosen over alternatives. No implementation jargon -- focus on customer experience and business logic.
6. **Alternatives considered (2-3 paragraphs).** For each meaningful alternative: describe it fairly, explain the trade-offs, and articulate why the proposed solution is superior. Show intellectual honesty.
7. **Metrics (1-2 paragraphs).** Define 3-5 success metrics with current baseline, target, measurement method, and timeline. Explain what each metric tells you about customer impact.
8. **Risks (1-2 paragraphs).** Top risks with likelihood, impact, and specific mitigation plans. Include what you would do if a key assumption proves wrong.
9. **Timeline (1 paragraph).** High-level phases with milestones. Acknowledge uncertainty and describe how you will manage it.
10. **Appendix.** Tables, diagrams, detailed metrics, cost models. This is where structured data lives.

### Amazon Writing Style Rules
- COMPLETE PARAGRAPHS ONLY in body. No bullet points, no numbered lists (except tenets). Appendix may use tables.
- Data-driven: every assertion backed by a specific number. "Revenue impact of $2.3M annually" not "large revenue impact."
- No weasel words: ban "significantly", "various", "some", "greatly", "many", "easy", "simple", "seamless"
- Customer-obsessed: every section connects back to customer impact
- Specificity over generality: name systems, teams, dates, dollar amounts, percentages with denominators
- "So what" test: for every fact, state the implication. For every metric, state the action it drives.
- Tenets as decision tools: reference tenets when explaining trade-offs
- Intellectual honesty: acknowledge weaknesses, uncertainties, and what you do not know
- Active voice: "We will build X" not "X will be built"

## Output Format
```
[Title: <Document Title>]
[Author: <name>] [Date: <date>]

[Customer obsession opening paragraph]

Context
[1-2 paragraphs]

The Problem
[2-3 paragraphs]

Tenets
1. [Tenet with "especially when" clause]
2. ...

Proposed Solution
[3-4 paragraphs]

Alternatives Considered
[2-3 paragraphs]

Success Metrics
[1-2 paragraphs with inline metrics]

Risks and Mitigations
[1-2 paragraphs]

Timeline
[1 paragraph]

Appendix
[Tables: metrics detail, cost model, dependency matrix, timeline Gantt, risk register]
```

## Delivery
Save as draft document. Send Slack DM with link and a one-sentence summary of the proposal. If a review meeting exists on the calendar, attach the document to the invite and remind attendees to read before the meeting.
