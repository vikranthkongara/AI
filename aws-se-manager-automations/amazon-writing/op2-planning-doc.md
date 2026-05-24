# OP2 Planning Document

Generate an OP2 (planning refinement) document that updates the OP1 plan with actuals, adjusts resource asks, and finalizes Q1 commitments.

## Data Sources
- Internal search: original OP1 document, leadership feedback on OP1, budget allocation decisions
- Taskei: updated backlog priorities, new items since OP1
- Pipelines/Apollo: updated operational metrics since OP1 submission
- Oncall: any new incident patterns or operational load changes
- Email/Slack: OP1 feedback from leadership, budget decisions communicated, hiring approvals/denials
- Calendar: OP2 submission deadline, Q1 sprint planning dates

## Instructions
1. **OP1 Recap (1 paragraph).** Summarize what was asked in OP1 and what was approved/denied. Be factual.
2. **Updated metrics.** Present any metrics that have materially changed since OP1 submission. Explain what changed and why it matters.
3. **Adjusted asks.** Based on OP1 feedback and budget decisions:
   - What asks were fully funded? Confirm delivery commitments.
   - What asks were partially funded? Describe adjusted scope and trade-offs.
   - What asks were denied? Describe impact and risk accepted.
4. **Finalized commitments.** For each funded initiative, specify: deliverable, owner, target date, success metric, dependency. This is a contract.
5. **Staffing plan.** Approved headcount with hiring timeline, backfill needs, contractor plans. Identify single-threaded owners for each initiative.
6. **Q1 deliverables.** Specific, measurable outcomes expected by end of Q1. These become the first WBR/QBR checkpoint.
7. **Risk update.** Any new risks since OP1. Updated mitigation for existing risks.

### Amazon Writing Style Rules
- Data-driven: compare OP1 projections to current actuals
- No weasel words: "We adjusted our timeline" must become "We moved the launch from March 15 to April 30 due to 6-week hiring delay for the SDE III role"
- Commitments are contracts: be precise about what you are committing to deliver
- Customer impact: for every adjustment, state the customer-facing consequence
- Specificity: exact dates, exact headcount, exact dollar amounts
- "So what": for every change from OP1, explain the implication

## Output Format
```
[Title: OP2 20__ - <Team Name>]

OP1 Recap and Decisions
[1-2 paragraphs summarizing OP1 outcome]

Updated Metrics
[1 paragraph on material changes since OP1]

Adjusted Plan
[2-3 paragraphs on funded/partially funded/denied items with trade-offs]

Finalized Commitments
[1-2 paragraphs in body, commitment table in appendix]

Staffing Plan
[1 paragraph on hiring timeline and owners]

Q1 Deliverables
[1-2 paragraphs with specific measurable outcomes]

Risks
[1 paragraph on new/updated risks]

Appendix
[Commitment tracker table, staffing timeline, Q1 milestone table, budget allocation]
```

## Delivery
Save as draft document. Send Slack DM with link and highlight any commitments that have changed from OP1. Flag dependencies that need cross-team alignment before Q1 starts.
