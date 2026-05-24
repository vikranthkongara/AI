# Individual Engagement Pulse Check

Gauge an individual engineer's engagement and well-being through observable signals, to proactively identify disengagement or burnout before it escalates.

## Data Sources
- Slack: Message frequency, channel participation, emoji usage, response patterns, activity hours
- CRUX CRs: PR velocity (submissions and reviews), quality of review comments, engagement in discussions
- Taskei: Task completion rate trends, time-to-start on new assignments, initiative-taking signals
- Calendar: Meeting attendance, camera-on patterns (if visible), 1:1 cancellation frequency
- Oncall system: Engagement during oncall shifts, response times to pages
- Email (Outlook): Response times, participation in optional threads

## Instructions
1. Establish a baseline for {{ENGINEER_NAME}} by looking at their typical patterns over the last 90 days, then compare the last 14 days against that baseline.
2. Analyze Slack patterns (last 14 days vs. baseline):
   - Message volume: Increasing, stable, or declining?
   - Channel participation breadth: Engaging in fewer channels?
   - Response time to messages: Getting slower?
   - Activity hours: Shifting later? More compressed? More erratic?
   - Tone signals: Less enthusiasm, shorter responses, fewer emoji reactions?
   - Social interaction: Still participating in non-work channels/banter?
3. Analyze CR patterns:
   - Submission frequency: Same pace or declining?
   - Review turnaround: Still prompt or increasingly delayed?
   - Review quality: Still thorough or becoming perfunctory (fewer comments, rubber-stamping)?
   - Code quality: More shortcuts, less documentation, fewer tests?
4. Analyze Taskei patterns:
   - Task pickup speed: Grabbing new tasks proactively or waiting to be assigned?
   - Completion velocity: Maintaining pace or slowing?
   - Initiative items: Still proposing improvements or just executing assigned work?
5. Check calendar signals:
   - 1:1 cancellations or reschedules by them (increased frequency?)
   - Optional meeting attendance (declining?)
   - Focus time: Are they blocking more time (healthy) or less (overwhelmed)?
6. Synthesize all signals into an engagement score and trend direction.
7. If concerning signals detected, suggest gentle conversation approaches - NOT confrontational check-ins.

## Output Format
```
## Engagement Pulse: {{ENGINEER_NAME}}
### Assessment Date: {{DATE}}
### Overall Engagement: [High / Moderate / Declining / Concerning]
### Trend: [Stable / Improving / Declining]

### Signal Dashboard
| Dimension | Baseline (90d avg) | Last 14 Days | Delta | Signal |
|-----------|-------------------|--------------|-------|--------|
| Slack activity | [X msgs/day] | [Y msgs/day] | [+/-Z%] | [Normal/Watch/Concern] |
| CR velocity | [X CRs/week] | [Y CRs/week] | [+/-Z%] | [Normal/Watch/Concern] |
| Review engagement | [quality level] | [quality level] | [change] | [Normal/Watch/Concern] |
| Task completion | [X tasks/sprint] | [Y tasks/sprint] | [+/-Z%] | [Normal/Watch/Concern] |
| Meeting participation | [pattern] | [pattern] | [change] | [Normal/Watch/Concern] |
| Work hours pattern | [typical range] | [current range] | [change] | [Normal/Watch/Concern] |

### Positive Signals
- [Any upticks or healthy patterns observed]

### Watch Signals
- [Patterns that are slightly off baseline but not alarming]

### Concerning Signals (if any)
- [Significant deviations that warrant attention]
- Possible explanations: [External project pressure, personal factors, team dynamics, etc.]

### Context to Consider
- [Recent events that could explain changes: reorg, project change, oncall, personal leave]

### Suggested Approach for Next 1:1
- [Gentle, non-invasive ways to check in]
- [Questions to ask that open the door without being confrontational]
- [Support to offer proactively]
```

## Delivery
Send as a Slack DM to me. Run weekly on Friday afternoon. If engagement level is "Concerning," send an additional alert immediately rather than waiting for the weekly cadence.
