# Team Communication Health Analysis

Analyze team communication patterns to identify information flow gaps, collaboration health, and opportunities to improve how the team shares knowledge.

## Data Sources
- Slack: Channel activity, DM patterns (volume not content), thread usage, cross-channel posting, response times
- CRUX CRs: Review interaction patterns, cross-pollination between sub-teams
- Taskei: Collaboration on shared tasks, dependency communication
- Calendar: Meeting interactions, who meets with whom
- Email (Outlook): Communication flow patterns (not content)

## Instructions
1. **Channel Activity Analysis**:
   - For each team Slack channel, measure:
     - Messages per day (trend over 30 days)
     - Unique participants (is everyone contributing or just a few?)
     - Thread usage rate (healthy teams use threads)
     - Unanswered questions (messages with ? that got no reply)
     - Response time to questions
   - Identify dead or underused channels
   - Identify channels with too much noise (signal-to-noise issues)
2. **Participation Distribution**:
   - Who are the top communicators? (healthy: distributed)
   - Who is silent? (potential engagement concern or just different style)
   - Is communication dominated by a few people?
   - Are there team members who only communicate in 1:1s but not in team channels?
3. **Cross-Team Communication**:
   - How much interaction happens with partner teams?
   - Are there dependency teams we should communicate with more?
   - Who are our bridges to other teams? (risk if only one person connects)
4. **Information Flow Gaps**:
   - Are decisions being made in DMs that should be in channels? (look for patterns where DM volume is high but channel discussion is low)
   - Are important updates reaching everyone? (channel membership vs. team size)
   - Is context from leadership/cross-team meetings being shared back?
5. **Collaboration Patterns from CRs**:
   - Are team members reviewing each other's code broadly, or only within sub-groups?
   - Is there healthy back-and-forth in CR discussions?
   - Are different perspectives represented in reviews?
6. **Communication Anti-Patterns**:
   - Over-reliance on synchronous communication (everything needs a meeting)
   - Under-documentation (decisions not written down)
   - Information hoarding (one person knows things but doesn't share proactively)

## Output Format
```
## Team Communication Health Report
### Team: {{TEAM_NAME}}
### Period: Last 30 days
### Overall Health: [Healthy / Adequate / Needs Attention]

### Channel Activity Summary
| Channel | Msgs/Day | Participants | Thread Rate | Unanswered Qs |
|---------|----------|-------------|-------------|---------------|
| #team-main | ... | .../[team size] | ...% | ... |
| #team-oncall | ... | ... | ...% | ... |
| #team-random | ... | ... | ...% | ... |

### Participation Distribution
- Most active: [Top 3 - healthy if not too concentrated]
- Least active: [Bottom 3 - consider if this is a concern]
- Participation Gini coefficient: [0=equal, 1=one person dominates]
- Assessment: [Well-distributed / Slightly concentrated / Dominated by few]

### Cross-Team Interaction Map
| Partner Team | Interaction Level | Key Connector | Backup Connector |
|-------------|-------------------|---------------|-----------------|
| [Team X] | High/Med/Low | [Person] | [Person or None] |

### Information Flow Assessment
- Decisions visible in public channels: [estimate %]
- Leadership context shared promptly: [Yes/Partially/No]
- Key gap: [Where information is getting stuck]

### Code Review Collaboration
- Average reviewers per CR: [count]
- Review network diversity: [Do people review broadly or in cliques?]
- Sub-group isolation: [Any isolated pairs/groups?]

### Identified Issues
1. **[Issue]**: [Description, evidence, impact]
   - Suggested fix: [Action]
2. **[Issue]**: [Description, evidence, impact]
   - Suggested fix: [Action]

### Positive Patterns
- [What's working well in team communication]

### Recommendations
1. [Specific action to improve communication]
2. [Specific action to improve communication]
3. [Specific action to improve communication]
```

## Delivery
Send as a Slack DM to me monthly, mid-month. Include specific actionable recommendations I can bring up in the next team retro or address in 1:1s.
