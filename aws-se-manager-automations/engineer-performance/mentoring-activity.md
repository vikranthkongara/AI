# Mentoring Activity Report

Track mentoring activities across the team: CR review coaching comments, pairing sessions, onboarding buddy assignments, knowledge sharing sessions, and informal mentoring signals. This data supports promotion narratives and helps identify who is growing others.

## Data Sources
- CRUX CRs: review comments (especially teaching/explanatory comments vs simple approvals)
- Calendar: pairing sessions, 1:1s with junior engineers, knowledge sharing meetings
- Taskei: onboarding buddy tasks, mentoring-related tickets
- Slack: help provided in team channels, DM mentoring signals (channel activity only)
- Oncall system: shadow rotations, training rotations

## Instructions

1. Query CRUX CRs for the past 30 days. For each engineer acting as a reviewer, analyze:
   - Total CRs reviewed
   - Average comment length (longer comments often indicate teaching)
   - Comments containing explanations ("because", "the reason", "this pattern", "consider", "a better approach")
   - Comments with links to documentation or best practices
   - Reviews of junior engineers' code vs peer reviews
   - Ratio of "nit" comments vs substantive architectural feedback
   - Time to first review (responsiveness to others' CRs)

2. Check calendar for mentoring-related meetings:
   - Pairing sessions (meetings with exactly 2 attendees, titles containing "pair", "walk through", "review")
   - Knowledge sharing sessions (brown bags, tech talks, lunch-and-learns)
   - Onboarding meetings with new hires
   - Office hours or open Q&A sessions hosted

3. Query Taskei for:
   - Onboarding buddy assignments and completion status
   - Mentoring-tagged tasks
   - Tasks where senior engineers are listed as advisors/consultants
   - New hire ramp-up ticket completion rates (for their buddies)

4. Review oncall system for:
   - Shadow oncall rotations (training new oncallers)
   - Engineers who joined incidents to coach rather than resolve themselves

5. Slack channel analysis (public team channels only):
   - Detailed answers to technical questions
   - Proactive knowledge sharing (unprompted explanations)
   - Redirecting to documentation (teaching to fish)
   - Frequency of being tagged for help by others

6. Compile mentoring profile per engineer:
   - **Active mentors:** High coaching CR comments, regular pairing, leading knowledge shares
   - **Growing mentors:** Some teaching signals, could do more with encouragement
   - **Opportunity:** Little mentoring activity, may need discussion about expectations at their level

## Output Format

```
## Mentoring Activity Report
**Period:** Past 30 days
**Team:** [team name]

### Per-Engineer Mentoring Summary

| Engineer | CRs Reviewed | Coaching Comments | Pairing Sessions | Knowledge Shares | Onboarding Work |
|----------|-------------|-------------------|------------------|------------------|-----------------|
| [name]   | [n]         | [n]               | [n hours]        | [n]              | [yes/no]        |

### Mentoring Leaders
1. **[name]** (Level: [L])
   - [Specific examples: "Provided 15 teaching comments on junior CRs, hosted 2 brown bags on service architecture"]
   - [Impact: "Helped [junior engineer] ship their first production CR independently"]

2. **[name]** (Level: [L])
   - [Specific examples]
   - [Impact]

### CR Review Quality
- Team average comments per review: [n]
- Engineers with highest coaching comment ratio: [list]
- Average time to first review: [hours] (team) | per engineer breakdown below
  - [name]: [hours]
  - [name]: [hours]

### Knowledge Sharing Sessions This Period
| Session | Presenter | Attendees | Topic |
|---------|-----------|-----------|-------|
| [date]  | [name]    | [n]       | [topic] |

### Onboarding Buddy Status
| New Hire | Buddy | Weeks Since Start | Ramp Tickets Complete | Status |
|----------|-------|-------------------|-----------------------|--------|
| [name]   | [name]| [n]               | [n/total]             | [on-track/needs-attention] |

### Observations
- [Patterns: e.g., "Mentoring concentrated in top 2 engineers, need to distribute"]
- [Gaps: e.g., "No brown bags scheduled in past 3 weeks"]
- [Wins: e.g., "New hire ramped to independent oncall in 4 weeks thanks to buddy program"]

### Recommendations
1. [e.g., "Include [engineer]'s mentoring data in promotion doc - strong L5 signal"]
2. [e.g., "Encourage [engineer] to host a knowledge share - they have deep expertise in [area]"]
3. [e.g., "Schedule pairing rotation for [junior] on [complex system]"]
```

## Delivery
Send the formatted report as a Slack DM to me. This is performance review input data - do not share with the team. If any engineer at L5+ has minimal mentoring signals, flag for 1:1 discussion as this is typically a promotion expectation.
