# Risk Flags

Engineers with declining output, increased oncall pages, long periods without CRs, potential burnout signals, and other early warning indicators that require manager attention.

## Data Sources
- **CRUX CRs**: CR frequency and volume trends per engineer
- **Taskei**: Task completion trends, velocity changes, ticket staleness
- **Oncall System**: Page frequency, after-hours pages, repeat incidents
- **Calendar**: Meeting load, work-outside-hours patterns, PTO usage
- **Slack**: Activity patterns, responsiveness changes, tone/engagement changes
- **Pipelines/Apollo**: Deployment activity changes

## Instructions

1. **Monitor output decline signals**:
   - CRs authored per week trending down (>30% decline over 4 weeks)
   - Story points completed declining sprint over sprint
   - Longer time between CRs (gap exceeding personal average by 2x)
   - Smaller CR sizes (may indicate struggling with larger tasks)
   - Increased CR iteration count (more rework needed)
   - Tasks taking significantly longer than estimates

2. **Monitor burnout signals**:
   - Working outside normal hours consistently (commits/messages at odd times)
   - Oncall pages during sleep hours increasing
   - PTO not being used (no time off in 3+ months)
   - Calendar overloaded (>6 hours of meetings per day)
   - Short, terse communications replacing previously detailed ones
   - Declining participation in optional team activities
   - Increasing oncall burden without relief

3. **Monitor engagement decline signals**:
   - Reduced Slack activity (fewer messages, less channel participation)
   - Fewer CR reviews given (disengaging from team responsibilities)
   - Missing or passive in meetings (camera off, no contributions)
   - Not volunteering for new work
   - Delayed responses to messages (increasing response times)
   - Not attending optional events they previously attended

4. **Monitor quality decline signals**:
   - Increase in post-merge bugs or reverts
   - More review feedback received (indicating sloppier initial submissions)
   - Test coverage declining in their CRs
   - Increased linting violations in their code
   - Oncall incidents caused by their recent changes

5. **Monitor isolation signals**:
   - No pairing or collaborative work in 2+ weeks
   - Working on solo tasks exclusively
   - Not asking for help when stuck (ticket stale but no outreach)
   - Reduced interaction with the rest of the team
   - Not participating in design discussions

6. **Monitor external risk factors**:
   - Team changes (losing a close collaborator, new manager)
   - Role changes they didn't ask for
   - Passed over for promotion recently
   - Heavy oncall rotation without break
   - Working on a project they expressed dissatisfaction with

7. **Severity classification**:
   - **Immediate**: Multiple strong signals - need 1:1 this week
   - **Watch**: 1-2 moderate signals - monitor and check in
   - **Informational**: Slight changes that may be temporary

## Output Format

```
# Risk Flags Report - [Date]

## Summary
- Engineers with immediate flags: [count]
- Engineers on watch list: [count]
- Engineers all clear: [count]
- New flags since last report: [count]
- Resolved flags since last report: [count]

## IMMEDIATE ATTENTION REQUIRED

### [Engineer Name] - [Risk Type: Burnout/Decline/Disengagement]
**Severity: IMMEDIATE**
**Flags detected:**
- [Flag 1]: [Specific evidence - e.g., "CR output dropped from 5/week to 1/week over last month"]
- [Flag 2]: [Specific evidence - e.g., "Working past midnight 4 of last 5 days (commit timestamps)"]
- [Flag 3]: [Specific evidence - e.g., "No PTO taken in 4 months"]

**Context:**
- Currently oncall: [Yes/No]
- Recent events: [team change, project change, heavy workload]
- Last 1:1 topics: [any relevant context from previous conversations]

**Recommended Action:**
- Schedule focused 1:1 this week (not standard agenda)
- Topics to cover: workload, wellbeing, support needed
- Potential interventions: [reduce scope, oncall break, PTO encouragement]

---

## WATCH LIST

### [Engineer Name] - [Risk Type]
**Severity: WATCH**
**Flags detected:**
- [Flag]: [evidence]

**Monitoring plan:**
- Check again in [X] days
- What to watch: [specific metric to track]
- Threshold for escalation to immediate: [condition]

---

## RECENTLY RESOLVED

### [Engineer Name]
- Previous flags: [what was flagged]
- Resolution: [what changed - output recovered, took PTO, workload reduced]
- Current status: Healthy

## Risk Factor Analysis

| Engineer | Output Trend | Burnout Signals | Engagement | Quality | Oncall Load | Overall |
|----------|-------------|-----------------|-----------|---------|-------------|---------|
| [name] | [OK/Down] | [None/Low/Med/High] | [OK/Declining] | [OK/Declining] | [Normal/Heavy] | [Clear/Watch/Immediate] |

## Team-Wide Patterns
- Team oncall burden: [normal/elevated] - [X] after-hours pages this month
- Team meeting load: [X] avg hours/day in meetings
- Team PTO health: [X] engineers haven't taken PTO in 60+ days
- Morale indicators: [observations from team interactions]

## Proactive Recommendations
1. [Engineer A needs oncall break - 3 rotations without relief]
2. [Engineer B should be encouraged to take PTO - 4 months since last day off]
3. [Team meeting load is high - consider canceling/consolidating X meetings]
4. [Engineer C may benefit from a new challenge - same project for 6 months]
5. [Review workload distribution - top 2 engineers doing 60% of the work]

## Important Caveats
- These are signals, not conclusions. Use them to guide conversations, not to make judgments.
- Always consider context that the data cannot capture (personal circumstances, hidden work).
- Some patterns are temporary and self-correcting - not every flag requires intervention.
- Approach with empathy and curiosity, not surveillance.
```

## Delivery
- Send as Slack DM to me every Monday and Thursday (twice weekly)
- IMMEDIATE flags: send alert as soon as detected (do not wait for scheduled report)
- This report is STRICTLY confidential - manager eyes only
- Never reference these metrics directly in conversations with engineers
- Use as conversation starters ("How are you feeling about workload?") not accusations
