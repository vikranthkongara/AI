# Career Growth Trajectory Check

Review an engineer's career growth trajectory over the past quarter, identify gaps against promotion criteria, and recommend stretch assignments.

## Data Sources
- Taskei: Completed tasks and projects over the last quarter, scope and complexity of work
- CRUX CRs: Code review quality, design doc contributions, mentoring signals in review comments
- Slack: Cross-team collaboration signals, mentoring conversations, leadership indicators
- Calendar: Meetings attended (design reviews, interviews, cross-team syncs) indicating scope expansion
- Oncall system: Operational maturity signals, incident leadership
- Email (Outlook): Participation in hiring loops, cross-org initiatives

## Instructions
1. Determine {{ENGINEER_NAME}}'s current level and target next level from Taskei profile or team records.
2. Query Taskei for all tasks completed by {{ENGINEER_NAME}} in the last 90 days. Categorize by: scope (individual/team/org), complexity (routine/moderate/high), and independence level.
3. Pull CRUX CRs authored in the last 90 days. Analyze for: design complexity, scope of change, quality of documentation, and whether they demonstrate next-level thinking.
4. Pull CRUX CRs where they were a reviewer. Look for: mentoring signals (helpful comments to junior engineers), architectural guidance, raising the bar on quality.
5. Check Slack for: cross-team interactions (breadth of influence), helping others (answering questions), driving discussions, proposing improvements.
6. Check calendar for: design review participation, interview panels, tech talks given, cross-team meetings led.
7. Check oncall system for: incident leadership, post-mortem contributions, operational improvements driven.
8. Map observations against the promotion criteria for their target level (scope, impact, leadership, technical depth).
9. Identify 2-3 specific gaps between current demonstrated behaviors and next-level expectations.
10. Recommend 2-3 concrete stretch assignments or opportunities that would help close those gaps.

## Output Format
```
## Career Growth Check: {{ENGINEER_NAME}}
### Current Level: {{LEVEL}} | Target: {{TARGET_LEVEL}}
### Assessment Period: Last 90 days

### Skills Demonstrated at Next Level
- [Specific examples with evidence]

### Growth Areas (Gaps to Close)
| Criteria | Current State | Target State | Gap |
|----------|--------------|--------------|-----|
| Scope | ... | ... | ... |
| Impact | ... | ... | ... |
| Leadership | ... | ... | ... |
| Technical Depth | ... | ... | ... |

### Evidence Summary
- **Complexity of work**: [Assessment with examples]
- **Independence**: [Assessment with examples]
- **Influence**: [Assessment with examples]
- **Mentoring**: [Assessment with examples]

### Recommended Stretch Assignments
1. [Assignment] - Closes gap in [criteria] because [reasoning]
2. [Assignment] - Closes gap in [criteria] because [reasoning]
3. [Assignment] - Closes gap in [criteria] because [reasoning]

### Suggested Conversation Points for Next 1:1
- [How to frame growth discussion constructively]
```

## Delivery
Send as a Slack DM to me. Mark as confidential - this is manager-eyes-only content for 1:1 preparation.
