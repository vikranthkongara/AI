# One-Pager

Generate a concise one-page document for getting alignment on a proposal: problem, solution, alternatives, metrics, and ask.

## Data Sources
- Internal search: related docs, prior art, org priorities
- Taskei: relevant backlog items, customer requests
- Pipelines/Apollo: current metrics that motivate the proposal
- Oncall: operational data supporting the problem statement
- Email/Slack: stakeholder context, prior discussions on this topic

## Instructions
1. **Problem statement (2-3 sentences).** What is broken or missing? Who is affected? Quantify the impact. No preamble -- start with the problem.
2. **Proposed solution (3-5 sentences).** What are we proposing? How does it solve the problem? What is the customer experience after implementation?
3. **Alternatives considered (2-3 options).** For each alternative: one sentence description, one sentence on why it was rejected. Show you did the work.
4. **Success metrics.** 2-3 measurable outcomes that prove the solution worked. Include current baseline, target, and measurement method.
5. **The ask.** What do you need from the reader? Be explicit: approval, headcount, budget, dependency commitment, or simply alignment.

### Amazon Writing Style Rules
- Brevity is respect: one page means one page. Every word must earn its place.
- Data-driven: problem statement must include a number (cost, frequency, customer impact)
- No weasel words: "better experience" must become "reduce task completion time from 12 clicks to 3 clicks"
- Specificity: name the system, the team, the metric, the date
- Customer-obsessed: frame the problem in terms of customer pain, not internal inconvenience
- "So what" test: if removing a sentence changes nothing, remove it

## Output Format
```
[Title: One-Pager - <Proposal Name>]
[Author: <name>] [Date: <date>]

Problem
[2-3 sentences with quantified impact]

Proposed Solution
[3-5 sentences describing the solution and customer outcome]

Alternatives Considered
1. [Option A] - [Why rejected]
2. [Option B] - [Why rejected]
3. [Option C] - [Why rejected]

Success Metrics
| Metric | Current | Target | Measurement |
|--------|---------|--------|-------------|
| ...    | ...     | ...    | ...         |

The Ask
[1-2 sentences: exactly what you need from the reader]
```

## Delivery
Send as Slack DM or email to the specified audience. If presenting in a meeting, note the calendar event where it will be discussed.
