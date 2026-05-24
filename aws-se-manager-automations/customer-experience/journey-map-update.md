# Customer Journey Map Update

Update the customer journey map with current data: identify friction points, moments of delight, drop-off stages, and improvement opportunities.

## Data Sources
- Internal search: existing journey map, funnel analytics, session recordings summary
- Apollo: latency by workflow step, error rates by API endpoint
- Oncall: customer-reported friction, repeat issues by workflow step
- Taskei: UX improvements in progress, known issues being addressed
- Email/Slack: customer feedback mentioning specific steps, usability study results

## Instructions
1. **Define the journey stages.** List the end-to-end customer journey stages for the primary use case (e.g., Discovery, Onboarding, Configuration, First Use, Daily Use, Advanced Use, Support).
2. **For each stage, capture:**
   - **Customer goal:** What is the customer trying to accomplish?
   - **Actions:** What steps does the customer take?
   - **Touchpoints:** What systems/interfaces does the customer interact with?
   - **Emotions:** Based on data (CSAT, feedback, support tickets), how does the customer feel? Cite evidence.
   - **Friction points:** Where do customers struggle? Quantify (error rate, drop-off rate, time-on-task vs expected).
   - **Moments of delight:** Where do customers express satisfaction or surprise? Cite feedback.
   - **Drop-off rate:** What percentage of customers leave the journey at this stage? Compare to prior period.
3. **Identify top 3 friction points.** For each: describe the pain, quantify the impact, hypothesize the root cause, propose an improvement.
4. **Identify moments of delight.** What is working well? How can we amplify these?
5. **Opportunities.** Based on the journey map update, what are the highest-impact improvements we could make? Rank by customer impact and feasibility.
6. **Changes since last update.** What has improved? What has degraded? What is new?

### Amazon Writing Style Rules
- Customer-obsessed: write from the customer's perspective. "The customer expects X but encounters Y" not "the system does Z"
- Data-driven: "37% of customers abandon at the configuration step (up from 28% last month)" not "many customers leave during setup"
- No weasel words: "confusing interface" must become "4 out of 5 usability test participants could not find the save button within 30 seconds"
- Specificity: name the exact screen, button, or step where friction occurs
- "So what": every friction point must have a proposed action
- Evidence-based emotions: do not guess how customers feel -- cite CSAT scores, feedback quotes, or behavioral data

## Output Format
```
Customer Journey Map Update - <Product/Service> - <Date>

JOURNEY OVERVIEW
| Stage | Customer Goal | Satisfaction | Drop-off | Change vs Prior |
|-------|--------------|-------------|----------|-----------------|
| ...   | ...          | ...         | ...      | ...             |

DETAILED STAGE ANALYSIS

[Stage 1: <Name>]
- Goal: [What customer wants to achieve]
- Actions: [Steps taken]
- Touchpoints: [Systems/interfaces]
- Satisfaction: [Score with evidence]
- Friction: [Specific issues with data]
- Delight: [What works well]
- Drop-off: [Rate and trend]

[Repeat for each stage]

TOP FRICTION POINTS
| Rank | Stage | Friction | Impact | Root Cause Hypothesis | Proposed Fix |
|------|-------|----------|--------|----------------------|--------------|
| 1    | ...   | ...      | ...    | ...                  | ...          |

MOMENTS OF DELIGHT
[What is working and how to amplify]

CHANGES SINCE LAST UPDATE
| Area | Previous | Current | Direction | Cause |
|------|----------|---------|-----------|-------|
| ...  | ...      | ...     | ...       | ...   |

RECOMMENDED IMPROVEMENTS
| Opportunity | Expected Impact | Effort | Priority |
|-------------|----------------|--------|----------|
| ...         | ...            | ...    | ...      |
```

## Delivery
Save as updated journey map document. Send Slack DM to product manager and UX lead with summary of changes and top opportunities. If a CX review meeting is scheduled, attach to the calendar invite.
