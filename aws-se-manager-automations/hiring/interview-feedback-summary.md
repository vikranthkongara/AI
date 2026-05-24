# Interview Feedback Summary

Compile recent interview feedback across the team's open roles: pass/fail rates, bar raiser concerns, common rejection reasons, and calibration insights.

## Data Sources
- Email/Outlook (interview feedback submissions, debrief outcomes, bar raiser notes)
- Calendar (completed interviews, debrief meetings)
- Taskei (interview-related tracking tasks)
- Slack DMs (interviewer discussions, debrief follow-ups)

## Instructions
1. Check email for interview feedback submitted in the past 30 days. For each completed loop, collect:
   - Candidate identifier (anonymized for the report)
   - Role and level
   - Interviewers (team members involved)
   - Individual interviewer verdicts (strong hire, hire, no hire, strong no hire)
   - Overall debrief outcome (hire, no hire, incomplete)
   - Bar raiser verdict and any concerns raised
2. Calculate aggregate metrics:
   - Overall pass rate (offers extended / loops completed)
   - Pass rate by role and level
   - Pass rate by interviewer (to detect calibration issues)
   - Bar raiser override rate (times BR disagreed with majority)
3. Analyze rejection reasons:
   - Categorize feedback themes (technical depth, system design, leadership principles, coding, communication)
   - Identify the most common rejection reasons
   - Track if the same rejection reasons appear repeatedly (may indicate sourcing mismatch)
4. Assess interviewer patterns:
   - Interviewers who are significantly more or less likely to give "hire" vs team average
   - Interviewers whose assessments frequently disagree with the debrief outcome
   - New interviewers who may need calibration support
5. Identify bar raiser concerns:
   - Themes in bar raiser feedback
   - Cases where BR raised the bar significantly
   - Patterns that suggest we need to adjust our sourcing or screening
6. Look for quality-of-hire signals:
   - Feedback consistency (do interviewers agree or frequently disagree?)
   - Strength of hire signals (mostly "hire" vs "strong hire")
   - Level appropriateness (feedback suggesting candidate is better suited for different level)
7. Check for any outstanding feedback not yet submitted (interviews completed but feedback missing).

## Output Format
```
## Interview Feedback Summary
**Period:** Last 30 days
**Loops Completed:** [N]
**Offers Extended:** [N]
**Pass Rate:** [X]%

### Aggregate Metrics
| Metric | Value | Previous Period | Trend |
|--------|-------|----------------|-------|
| Loops completed | [N] | [N] | [Arrow] |
| Pass rate | [X]% | [Y]% | [Arrow] |
| Strong hire rate | [X]% | [Y]% | [Arrow] |
| BR override rate | [X]% | [Y]% | [Arrow] |
| Avg feedback agreement | [X]% | [Y]% | [Arrow] |

### Results by Role
| Role | Level | Loops | Pass | Fail | Rate | Notes |
|------|-------|-------|------|------|------|-------|

### Recent Loop Outcomes
| Date | Candidate (Anon) | Role | Outcome | Interviewer Agreement | BR Aligned? | Key Factor |
|------|-------------------|------|---------|----------------------|-------------|-----------|

### Rejection Reason Analysis
| Reason Category | Count | % of Rejections | Roles Affected | Trend |
|----------------|-------|-----------------|----------------|-------|
| Technical depth insufficient | [N] | [X]% | [Roles] | [Arrow] |
| System design gaps | [N] | [X]% | [Roles] | [Arrow] |
| Leadership principles | [N] | [X]% | [Roles] | [Arrow] |
| Coding/implementation | [N] | [X]% | [Roles] | [Arrow] |
| Communication/collaboration | [N] | [X]% | [Roles] | [Arrow] |
| Level mismatch | [N] | [X]% | [Roles] | [Arrow] |

### Interviewer Calibration
| Interviewer | Interviews (30d) | Hire Rate | vs Team Avg | Agreement w/ Outcome | Flag |
|-------------|-----------------|-----------|-------------|---------------------|------|
[Sorted by deviation from average]

### Interviewers Potentially Needing Calibration
| Interviewer | Concern | Evidence | Recommended Action |
|-------------|---------|----------|-------------------|
| [Name] | Consistently lenient | Hire rate 40% above team avg | Shadow experienced interviewer |
| [Name] | Consistently strict | Hire rate 30% below team avg | Calibration discussion |

### Bar Raiser Insights
| Theme | Frequency | Impact | Implication |
|-------|-----------|--------|-------------|
| [Theme] | [N] times | [Overturned N decisions] | [What to adjust] |

### Outstanding Feedback (Missing)
| Interview Date | Candidate | Interviewer | Days Overdue |
|---------------|-----------|-------------|--------------|

### Level Calibration
| Candidate | Targeted Level | Feedback Suggests | Interviewers Noting |
|-----------|---------------|-------------------|--------------------| 

### Recommendations
1. [Sourcing adjustment: e.g., "Increase technical screening bar - 60% of rejections are technical depth"]
2. [Calibration action: e.g., "Schedule calibration session for [Name] - significant deviation from team"]
3. [Process improvement: e.g., "Add system design phone screen for L6+ candidates to reduce loop waste"]

### Sourcing Quality Indicators
- Candidates meeting bar: [X]%
- Average number of strong signals per successful candidate: [N]
- Most effective sourcing channel: [Channel]
```

## Delivery
Send the full report as a Slack DM to me every other Friday. Send immediate alerts if pass rate drops below 20% for any role (indicates sourcing/screening problem) or if feedback is overdue by more than 48 hours.
