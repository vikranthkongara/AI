# Collaboration Score

Cross-team contributions, helping others unblock, Slack responsiveness, meeting participation, and overall collaboration health per engineer.

## Data Sources
- **CRUX CRs**: Cross-team reviews given, collaborative CRs (multiple authors), helping others' CRs get merged
- **Taskei**: Cross-team ticket contributions, helping others on blocked items
- **Slack**: Response times to questions, helping in channels, proactive communication
- **Calendar**: Meeting attendance, cross-team meetings, 1:1s with non-team members
- **Email (Outlook)**: Cross-team communication, timely responses to requests

## Instructions

1. **Measure cross-team contributions**:
   - CRs reviewed for engineers outside the team
   - CRs authored that involve other teams' services
   - Taskei tickets contributed to outside own team's board
   - Design reviews attended for other teams
   - Contributions to shared libraries or platforms

2. **Measure helping behaviors (within team)**:
   - Unblocking others: responding to review requests quickly, answering questions
   - Pair programming sessions (from calendar)
   - Offering to help when others are stuck (Slack evidence)
   - Taking on tasks to help teammates meet deadlines
   - Sharing knowledge proactively (not just when asked)

3. **Measure communication responsiveness**:
   - Average response time to Slack DMs from team members
   - Average response time to review requests
   - Response time to questions in team channels
   - Email response time to cross-team requests
   - Follow-through on commitments (did they do what they said they would?)

4. **Measure meeting participation**:
   - Attendance rate at team ceremonies (standup, planning, retro)
   - Active participation (not just present but contributing)
   - Cross-team meeting participation
   - Leading or facilitating discussions
   - Coming prepared vs passive attendance

5. **Measure collaborative work patterns**:
   - Frequency of reaching out to others before making big decisions
   - Seeking feedback early (design docs shared in draft)
   - Acknowledging others' contributions
   - Conflict resolution (constructive CR disagreements vs adversarial)
   - Inclusive behavior (pulling in others who should be involved)

6. **Identify collaboration anti-patterns**:
   - Working in isolation for extended periods without communication
   - Consistently slow to respond to team requests
   - Blocking others by not completing reviews or answering questions
   - Not attending team meetings regularly
   - Making unilateral decisions without consulting stakeholders

## Output Format

```
# Collaboration Score Report - [Period: Last 30 Days]

## Team Summary
- Team collaboration health: [Strong/Moderate/Needs Improvement]
- Cross-team contributions this period: [count]
- Avg review response time: [hours]
- Avg Slack response time: [hours]
- Team members with strong collaboration: [count]
- Team members needing collaboration coaching: [count]

## Per-Engineer Collaboration Profile

### [Engineer Name]

**Collaboration Score: [X]/10** (composite of below metrics)

| Dimension | Score | Evidence | Trend |
|-----------|-------|----------|-------|
| Cross-team work | [X/10] | [X] cross-team CRs, [Y] external reviews | [arrow] |
| Helping others | [X/10] | Unblocked [X] teammates, [Y] help messages | [arrow] |
| Responsiveness | [X/10] | [X]h avg review, [Y]h avg Slack reply | [arrow] |
| Meeting participation | [X/10] | [X]% attendance, [quality assessment] | [arrow] |
| Proactive communication | [X/10] | [evidence of proactive sharing/asking] | [arrow] |

**Collaboration Strengths:**
- [Consistently first to review teammates' CRs]
- [Active in helping junior engineers in Slack]
- [Excellent cross-team relationship with Team X]

**Collaboration Growth Areas:**
- [Slow to respond to review requests (avg Xh vs team avg Yh)]
- [Tends to work in isolation - 2 weeks without seeking feedback]
- [Missed 3 standups this month without notice]

**Notable Collaboration Events:**
- Helped [engineer] unblock on [task] by [action taken]
- Led cross-team design discussion with [Team X] on [topic]
- Shared [knowledge/doc/tool] proactively with team

---
(repeat for each engineer)

## Collaboration Leaderboard

| Rank | Engineer | Score | Top Strength |
|------|----------|-------|-------------|
| 1 | [name] | [X/10] | [description] |
| 2 | [name] | [X/10] | [description] |

## Cross-Team Interaction Map
- [Team A]: [X] interactions (reviews, meetings, shared work)
- [Team B]: [X] interactions
- [Team C]: [X] interactions
- Teams we should collaborate more with: [Team D] (dependency but low interaction)

## Communication Health

| Engineer | Slack Response | Review Response | Email Response | Status |
|----------|--------------|-----------------|----------------|--------|
| [name] | [hrs] | [hrs] | [hrs] | [Good/Needs improvement] |

## Anti-Patterns Detected
- [Engineer A]: No Slack activity in team channels for [X] days
- [Engineer B]: [X] review requests unanswered for >48h
- [Engineer C]: Missed [X]% of team meetings this period

## Recommendations
- [Engineer A]: Discuss collaboration in 1:1 - working too much in isolation
- [Engineer B]: Recognize their exceptional helping behavior publicly
- [Team]: Schedule more pairing sessions to increase collaboration
- [Team]: Consider async standup to accommodate different work patterns
- [Process]: Set team norm for review response within [X] business hours
```

## Delivery
- Send as Slack DM to me on the 1st of each month (monthly report)
- Use for 1:1 preparation and performance review evidence
- This is manager-only data - collaboration scores should not be shared as rankings
- Use trends over time rather than single snapshots for performance discussions
