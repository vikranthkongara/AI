# Two-Pager

Generate a two-page proposal document that extends the one-pager format with implementation details, timeline, risks, and cost estimate.

## Data Sources
- Internal search: architecture docs, related proposals, org priorities, cost models
- Taskei: related work items, estimated effort for similar past projects
- Pipelines/Apollo: current system metrics, capacity data
- Oncall: operational complexity that informs implementation risk
- Email/Slack: stakeholder feedback, prior discussions, dependency conversations
- CRs: related code changes that inform scope

## Instructions
1. **Problem statement (2-3 sentences).** Quantified customer pain. Same rigor as one-pager.
2. **Proposed solution (1 paragraph).** What we are building and why this approach. Customer-facing outcome.
3. **Alternatives considered (2-3 options).** Each with rationale for rejection -- show due diligence.
4. **Implementation plan.** Break into phases or milestones. For each: scope, owner, dependencies, duration. Be specific enough that someone could estimate a timeline from this.
5. **Timeline.** Week-by-week or month-by-month depending on scope. Include key milestones, review points, launch date.
6. **Risks (top 3-5).** Each with: description, likelihood (high/medium/low), impact (high/medium/low), mitigation plan.
7. **Dependencies.** Named teams, specific deliverables needed, committed dates (or "uncommitted" if not yet agreed).
8. **Cost estimate.** People-weeks of effort, infrastructure cost delta, any tooling/license costs. Total investment and expected payback period.
9. **Success metrics.** Measurable outcomes with baseline, target, and timeline for measurement.
10. **The ask.** Explicit request to the reader.

### Amazon Writing Style Rules
- Data-driven: every estimate backed by analogy, data, or explicit assumption
- No weasel words: "a few weeks" must become "3 weeks (based on similar work in Q2 that took 14 days)"
- Specificity: name owners, dates, dollar amounts, team names
- Customer-obsessed: implementation details serve the reader, but frame outcomes for the customer
- Honest about unknowns: if an estimate is uncertain, say so and explain what would resolve the uncertainty
- "So what" for costs: tie every investment back to the customer outcome it enables

## Output Format
```
[Title: Two-Pager - <Proposal Name>]
[Author: <name>] [Date: <date>]

Problem
[2-3 sentences with quantified impact]

Proposed Solution
[1 paragraph describing solution and customer outcome]

Alternatives Considered
1. [Option A] - [Why rejected]
2. [Option B] - [Why rejected]

Implementation Plan
Phase 1: [Scope, owner, duration]
Phase 2: [Scope, owner, duration]
Phase 3: [Scope, owner, duration]

Timeline
| Week/Month | Milestone | Owner | Dependencies |
|------------|-----------|-------|--------------|
| ...        | ...       | ...   | ...          |

Risks
| Risk | Likelihood | Impact | Mitigation |
|------|-----------|--------|------------|
| ...  | ...       | ...    | ...        |

Dependencies
[Named teams and specific deliverables with dates]

Cost Estimate
[People-weeks, infrastructure, total investment, payback]

Success Metrics
| Metric | Baseline | Target | Measure By |
|--------|----------|--------|------------|
| ...    | ...      | ...    | ...        |

The Ask
[Explicit request]
```

## Delivery
Save as draft document. Send Slack DM or email to specified recipients. If a review meeting is scheduled, attach to the calendar invite.
