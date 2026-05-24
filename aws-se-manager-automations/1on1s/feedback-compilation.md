# Peer Feedback Compilation

Compile peer feedback received about an engineer from various collaboration touchpoints to inform 1:1 discussions and performance reviews.

## Data Sources
- CRUX CRs: Review comments on their CRs (tone, praise, concerns), their review comments on others' CRs
- Slack: Public channel interactions, shout-outs, questions directed to them, collaborative threads
- Taskei: Collaborative tasks, cross-team work, dependencies where they were involved
- Oncall system: Handoff notes, incident collaboration feedback
- Email (Outlook): Any forwarded praise, escalation threads involving them

## Instructions
1. Pull all CRUX CRs authored by {{ENGINEER_NAME}} in the last 30 days. Extract reviewer comments that indicate: quality praise, design concerns, recurring patterns (positive or negative), teaching moments.
2. Pull all CRUX CRs reviewed by {{ENGINEER_NAME}} in the last 30 days. Analyze their review style: thoroughness, tone, helpfulness, mentoring quality. Note any feedback from CR authors about their reviews.
3. Search Slack channels the engineer is active in for: direct mentions with context, shout-outs or thanks, questions specifically directed to them (indicates expertise recognition), any friction or miscommunication signals.
4. Check Taskei for collaborative tasks. Look at comments from collaborators about working together, dependency handoff quality, and communication timeliness.
5. Review oncall handoff notes for any feedback about their oncall performance from teammates.
6. Check email for any forwarded praise or concerns from stakeholders or partner teams.
7. Categorize all feedback into themes: technical quality, collaboration, communication, reliability, mentoring, areas for improvement.
8. For each theme, provide specific anonymized examples (remove names of feedback givers unless it's public praise).

## Output Format
```
## Peer Feedback Compilation: {{ENGINEER_NAME}}
### Period: Last 30 days
### Sources Analyzed: [count] CRs, [count] Slack interactions, [count] collaborative tasks

### Positive Themes
#### Theme 1: [e.g., "Technical Thoroughness"]
- Evidence: [2-3 anonymized examples]
- Frequency: [How often this comes up]

#### Theme 2: [e.g., "Helpful to Others"]
- Evidence: [2-3 anonymized examples]
- Frequency: [How often this comes up]

### Growth Area Themes
#### Theme 1: [e.g., "Communication Timeliness"]
- Evidence: [2-3 anonymized examples]
- Suggested coaching approach: [How to bring this up constructively]

### Notable Quotes (Anonymized)
- "[Direct quote from CR or Slack that captures feedback well]"
- "[Another notable quote]"

### Summary for 1:1 Discussion
- Top strength to recognize: [...]
- Area to coach on: [...]
- Suggested framing: [...]
```

## Delivery
Send as a Slack DM to me. This is confidential manager preparation material. Do not share with the engineer directly - I will use this to inform my coaching conversations.
