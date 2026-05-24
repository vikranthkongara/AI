# Interview Loop Schedule Check

Review upcoming interview loops involving team members, ensure adequate coverage, identify scheduling conflicts, and flag interviewers needing calibration or training.

## Data Sources
- Calendar (scheduled interviews, debrief sessions)
- Email/Outlook (interview assignments, recruiter communications)
- Taskei (interview-related tasks, calibration tracking)
- Slack DMs (interviewer availability discussions)

## Instructions
1. Check calendar for all interview-related events in the next 2 weeks involving team members:
   - Phone screens
   - On-site/virtual loop interviews
   - Debrief sessions
   - Bar raiser shadow sessions
2. For each team member, calculate interview load:
   - Number of interviews scheduled this week and next
   - Total interview hours (including prep and debrief)
   - Impact on sprint commitment (interviews during focus blocks)
3. Check for scheduling conflicts:
   - Interviews overlapping with critical team meetings
   - Multiple interviews on the same day for one person
   - Interviews during oncall shifts
   - Interviews conflicting with sprint demos or planning
4. Verify loop coverage:
   - Each loop has all required competency areas covered
   - Bar raiser is assigned
   - No single team member is assigned to multiple slots in the same loop
5. Identify interviewers needing attention:
   - New interviewers who haven't completed shadow training
   - Interviewers who haven't interviewed in > 3 months (may need refresher)
   - Interviewers with unusually high or low pass rates (potential calibration issue)
   - Interviewers who have declined or rescheduled frequently
6. Check email for any recruiter requests for additional interviewer coverage or changes to scheduled loops.

## Output Format
```
## Interview Loop Schedule Report
**Date:** [Date]
**Period:** Next 2 weeks

### Upcoming Interviews
| Date | Candidate (Role) | Loop Type | Team Interviewers | Competency | Status |
|------|------------------|-----------|-------------------|------------|--------|

### Interview Load by Team Member
| Engineer | This Week | Next Week | Total Hours | Sprint Impact | Notes |
|----------|-----------|-----------|-------------|---------------|-------|
| [Name]   | [N]       | [N]       | [X hrs]     | [Low/Med/High] | |

### Scheduling Conflicts
| Engineer | Interview Date/Time | Conflict With | Severity | Resolution |
|----------|--------------------|--------------|---------|-----------| 

### Coverage Gaps
| Loop Date | Candidate | Missing Competency | Suggested Interviewer |
|-----------|-----------|-------------------|----------------------|

### Interviewer Health
| Engineer | Last Interview | Total This Quarter | Pass Rate | Status |
|----------|---------------|-------------------|-----------|--------|

### Interviewers Needing Calibration/Training
| Engineer | Reason | Recommended Action | Priority |
|----------|--------|-------------------|----------|
[e.g., high deviation from team average pass rate, new to interviewing, etc.]

### Debrief Sessions
| Date | Candidate | Attendees | Bar Raiser | All Feedback In? |
|------|-----------|-----------|------------|-----------------|

### Recommended Actions
1. [Action: e.g., "Reschedule Alice's Thursday interview - conflicts with sprint demo"]
2. [Action: e.g., "Bob hasn't interviewed in 4 months - assign next available loop"]
3. [Action: e.g., "Schedule calibration session for Carol - pass rate significantly above team average"]

### Interview Capacity Summary
- Total interview slots available this week: [N]
- Slots filled: [N]
- Team members at max interview load: [Names]
- Team members available for additional loops: [Names]
```

## Delivery
Send the full report as a Slack DM to me every Monday morning. Send immediate alerts for any coverage gaps in loops scheduled within 48 hours.
