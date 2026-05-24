# Goal Setting Document

Generate a goal-setting document with SMART goals aligned to org priorities, success metrics, development objectives, and timeline checkpoints.

## Data Sources
- Internal search: org-level OKRs, team charter, VP goals, level expectations
- Taskei: current roadmap, upcoming initiatives, tech debt backlog
- Pipelines/Apollo: operational targets, current baseline metrics
- Email/Slack: manager feedback, skip-level guidance, career development discussions
- Calendar: performance review cycle dates, checkpoint cadence

## Instructions
1. **Alignment context (1 paragraph).** Connect individual goals to team OKRs and org priorities. Show the line of sight from this person's work to customer impact.
2. **Business goals (3-5 goals).** For each goal:
   - **Specific:** Exactly what will be delivered or achieved
   - **Measurable:** Quantified success criteria (not "improve X" but "reduce X from A to B")
   - **Achievable:** Within the person's scope and resources
   - **Relevant:** Tied to team/org priority (name which one)
   - **Time-bound:** Specific deadline or checkpoint date
3. **Development goals (1-2 goals).** Skills or behaviors to develop for career growth. Aligned to next-level expectations. Include concrete actions (not "get better at X" but "lead 2 design reviews for cross-team systems by Q3").
4. **Stretch goals (1-2 goals).** Ambitious outcomes that would represent exceptional performance. Clear on what "stretch" means vs "expected."
5. **Success metrics table.** For each goal: metric, baseline, target, measurement method, checkpoint dates.
6. **Timeline checkpoints.** Monthly or quarterly check-in points with expected progress at each stage. Define what "on track" looks like at each checkpoint.
7. **Support needed.** Resources, training, mentorship, or access needed to achieve these goals.

### Amazon Writing Style Rules
- Specificity: "Deliver caching tier for ProductService reducing p99 from 800ms to 200ms by March 30" not "improve service performance"
- Data-driven: every goal has a measurable outcome with a number
- No weasel words: "significantly improve" is banned -- use specific targets
- Customer-obsessed: connect each goal to customer impact
- "So what" for each goal: why does this matter to the team/org/customer
- Honest about stretch: clearly differentiate between expected performance and exceptional performance

## Output Format
```
[Title: Goals - <Name> - <Period>]
[Level: <level>] [Manager: <name>] [Date: <date>]

Alignment
[1 paragraph connecting to org priorities]

Business Goals
1. [Goal statement]
   - Success metric: [specific measurable outcome]
   - Aligned to: [team OKR or org priority]
   - Deadline: [date]

2. [Goal statement]
   ...

Development Goals
1. [Goal statement]
   - Actions: [specific steps]
   - Evidence of achievement: [how we know it's done]
   - Timeline: [date]

Stretch Goals
1. [Goal statement]
   - What "stretch" means: [differentiate from expected]
   - Success metric: [measurable outcome]

Success Metrics
| Goal | Metric | Baseline | Target | Checkpoint 1 | Checkpoint 2 | Final |
|------|--------|----------|--------|--------------|--------------|-------|
| ...  | ...    | ...      | ...    | ...          | ...          | ...   |

Timeline
| Month | Expected Progress | Check-in Date |
|-------|-------------------|---------------|
| ...   | ...               | ...           |

Support Needed
- [Resources, training, access required]
```

## Delivery
Save as draft document. Send Slack DM with link to the employee and their manager. Flag any goals that need further discussion or refinement.
