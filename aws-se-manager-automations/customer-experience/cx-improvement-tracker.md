# CX Improvement Initiative Tracker

Track CX improvement initiatives: hypothesis, experiment status, before/after metrics, customer impact, and next steps.

## Data Sources
- Taskei: CX improvement work items, experiment tickets, A/B test configurations
- Pipelines: deployment status of CX improvements
- Apollo: metrics for services with active experiments
- Internal search: experiment framework results, A/B test dashboards
- Email/Slack: experiment results shared, stakeholder feedback on changes
- Oncall: any issues introduced by CX changes

## Instructions
1. **Active initiatives inventory.** List all in-flight CX improvement initiatives. For each:
   - Name and brief description
   - Hypothesis: "We believe [change] will [outcome] for [customer segment] because [rationale]"
   - Status: Planning / In Development / Experiment Running / Analyzing Results / Shipping / Complete
   - Owner
   - Start date and expected completion
2. **Metrics before/after.** For initiatives that have launched or are in experiment:
   - Baseline metric (before the change)
   - Current metric (after the change or during experiment)
   - Statistical significance (if A/B test)
   - Sample size and duration
3. **Customer impact assessment.** For each completed or in-progress initiative:
   - Quantified customer impact (customers affected, improvement magnitude)
   - Qualitative signals (feedback, support ticket reduction, NPS change)
   - Unexpected effects (positive or negative)
4. **Decision needed.** For initiatives awaiting a decision:
   - Ship (results positive, ready to go to 100%)
   - Iterate (results mixed, needs refinement)
   - Kill (hypothesis disproven, move on)
   Include the evidence supporting the recommendation.
5. **Pipeline view.** What is coming next? Initiatives in planning that have not started yet. Prioritized by expected impact.
6. **Lessons learned.** From recently completed experiments: what did we learn that informs future work?

### Amazon Writing Style Rules
- Data-driven: "Reduced task completion time from 4.2 minutes to 1.8 minutes (57% reduction, p<0.01, n=12,400)" not "made it faster"
- No weasel words: "positive results" must become "12% increase in completion rate (from 73% to 82%)"
- Hypothesis-driven: every initiative must have a testable hypothesis stated upfront
- Honest about failures: initiatives that did not work are learning opportunities -- report them with the same rigor
- "So what": for every result, state the decision it drives (ship/iterate/kill)
- Customer-obsessed: frame results in customer terms, not system terms

## Output Format
```
CX Improvement Tracker - <Date>

SUMMARY
[2-3 sentences: active initiatives count, key results this period, decisions needed]

ACTIVE INITIATIVES
| Initiative | Hypothesis | Status | Owner | Start | ETA | Result |
|-----------|-----------|--------|-------|-------|-----|--------|
| ...       | ...       | ...    | ...   | ...   | ... | ...    |

RESULTS DETAIL

[Initiative 1: <Name>]
- Hypothesis: [We believe...]
- Metrics:
  | Metric | Before | After | Delta | Significance |
  |--------|--------|-------|-------|--------------|
  | ...    | ...    | ...   | ...   | ...          |
- Customer impact: [Quantified]
- Recommendation: [Ship / Iterate / Kill]
- Evidence: [Why this recommendation]

[Repeat for each initiative with results]

DECISIONS NEEDED
| Initiative | Recommendation | Evidence | Deadline |
|-----------|---------------|----------|----------|
| ...       | ...           | ...      | ...      |

PIPELINE (upcoming)
| Initiative | Hypothesis | Expected Impact | Priority | Planned Start |
|-----------|-----------|----------------|----------|---------------|
| ...       | ...       | ...            | ...      | ...           |

LESSONS LEARNED
- [Learning 1: what we tried, what happened, what it means]
- [Learning 2: ...]
```

## Delivery
Post to CX team Slack channel weekly. Send Slack DM to product manager highlighting decisions needed. Save to file for historical tracking of experiment results.
