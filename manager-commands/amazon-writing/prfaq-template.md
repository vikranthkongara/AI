# PR/FAQ (Press Release / Frequently Asked Questions)

Generate a PR/FAQ document in Amazon's Working Backwards format: a future press release announcing the completed product, followed by external and internal FAQ sections.

## Data Sources
- Internal search: existing product docs, customer research, competitive landscape
- Taskei: related feature requests, customer-reported pain points
- Email/Slack: customer feedback, stakeholder input on the proposal
- Oncall: current pain points that motivate the proposal (if operational improvement)

## Instructions

### Press Release Section
1. **Headline.** One sentence that a customer would understand. No jargon. Names the customer benefit.
2. **Subheadline.** One sentence expanding on who the customer is and what they gain.
3. **Date and location line.** "[City] -- [Date]"
4. **Opening paragraph.** Summarize the launch: what is it, who is it for, what problem does it solve, how does the customer access it.
5. **Problem paragraph.** Describe the customer's current pain in specific terms. Use data if available (e.g., "Today, customers spend an average of 23 minutes completing a task that should take 3 minutes").
6. **Solution paragraph.** Describe how the product solves the problem. Focus on customer experience, not implementation.
7. **Quote from leadership.** A fictional quote from a leader explaining why this matters.
8. **How it works.** 2-3 sentences on the customer experience (not technical architecture).
9. **Customer quote.** A fictional quote from a target customer explaining the benefit in their words.
10. **Call to action.** How to get started.

### FAQ Section
11. **External FAQ (5-8 questions).** Questions a customer would ask: pricing, availability, compatibility, migration, data privacy, limitations.
12. **Internal FAQ (5-8 questions).** Questions stakeholders would ask: cost to build, timeline, team size, dependencies, risks, why now, why not alternative approach, how we measure success.

### Amazon Writing Style Rules
- Customer-obsessed: the entire PR is written from the customer's perspective
- No jargon: if a customer would not understand a term, replace it
- Specific: "reduces time from 23 minutes to 3 minutes" not "makes it faster"
- No weasel words: no "easy", "simple", "seamless" without defining what that means
- Data-driven: include projected metrics where possible
- Honest about limitations: FAQ should address real concerns, not softball questions

## Output Format
```
[PRESS RELEASE]

Headline: [One customer-facing sentence]
Subheadline: [Customer + benefit]

[City] -- [Date] -- [Opening paragraph]

[Problem paragraph]

[Solution paragraph]

"[Leadership quote]" -- [Name, Title]

[How it works paragraph]

"[Customer quote]" -- [Customer persona name, role]

[Call to action]

---

[FREQUENTLY ASKED QUESTIONS]

External (Customer) FAQ
Q1: [Question]
A1: [Answer]
...

Internal (Stakeholder) FAQ
Q1: [Question]
A1: [Answer]
...
```

## Delivery
Save as draft document. Send Slack DM with link. Flag any FAQ questions where the answer requires additional research or a decision from leadership.
