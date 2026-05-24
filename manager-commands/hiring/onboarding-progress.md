# New Hire Onboarding Progress

Track onboarding progress for new team members: days since start, key milestones completed, first contributions, buddy check-ins, and 30/60/90 day assessments.

## Data Sources
- Taskei (onboarding task lists, milestone tracking)
- CRUX CRs (first code contributions, review activity)
- Calendar (1:1s, buddy meetings, onboarding sessions)
- Email/Outlook (onboarding communications, training completions)
- Slack DMs (buddy updates, new hire questions/concerns)
- Pipelines (first deployment by new hire)

## Instructions
1. Identify all team members who started within the last 90 days (currently in onboarding window).
2. For each new hire, check their onboarding task list in Taskei:
   - Total onboarding tasks assigned
   - Tasks completed vs remaining
   - Overdue tasks (past their target date)
   - Blocked tasks
3. Check CRUX for code contribution milestones:
   - First CR created (date and description)
   - First CR merged/approved
   - Number of CRs authored to date
   - Code review participation (reviews given)
   - Packages/services they've contributed to
4. Check Pipelines for deployment milestones:
   - First deployment to any environment
   - First production deployment
5. Check calendar for relationship-building activities:
   - 1:1 meetings with manager (frequency and consistency)
   - Buddy check-ins (are they happening as scheduled?)
   - Meet-and-greets with cross-team stakeholders
   - Training sessions attended
6. Assess progress against 30/60/90 day milestones:
   - **30 days:** Environment setup, first CR, met team, completed required training
   - **60 days:** Independent task completion, meaningful code contributions, oncall shadow
   - **90 days:** Owning a feature/component, participating in design discussions, oncall ready
7. Check email and Slack for any concerning signals:
   - New hire expressing confusion or frustration
   - Buddy flagging concerns
   - Training not being completed on schedule
8. Identify areas where additional support may be needed.

## Output Format
```
## New Hire Onboarding Progress
**Date:** [Date]
**Active Onboarders:** [N]

### Summary
| Name | Start Date | Day # | Phase | Overall Progress | Concern Level |
|------|-----------|-------|-------|-----------------|---------------|
| [Name] | [Date] | [N] | [30/60/90] | [On Track/Behind/Ahead] | [None/Low/Medium/High] |

### Detailed Progress

#### [New Hire Name]
**Start Date:** [Date] | **Day:** [N] | **Role:** [Title] | **Buddy:** [Name]

##### Milestone Progress
| Milestone | Target Day | Status | Actual Date | Notes |
|-----------|-----------|--------|-------------|-------|
| Dev environment setup | Day 3 | [Done/Pending] | [Date] | |
| Required training complete | Day 7 | [Done/Pending] | [Date] | |
| First CR created | Day 14 | [Done/Pending] | [Date] | [CR link] |
| First CR merged | Day 21 | [Done/Pending] | [Date] | [CR link] |
| First independent task | Day 30 | [Done/Pending] | [Date] | |
| Oncall shadow complete | Day 45 | [Done/Pending] | [Date] | |
| First production deploy | Day 60 | [Done/Pending] | [Date] | |
| Own a component | Day 75 | [Done/Pending] | [Date] | |
| Oncall ready | Day 90 | [Done/Pending] | [Date] | |

##### Code Contributions
| Metric | Value | Expected at Day [N] | Status |
|--------|-------|--------------------|---------| 
| CRs authored | [N] | [Expected] | [On Track/Behind] |
| CRs merged | [N] | [Expected] | [On Track/Behind] |
| Reviews given | [N] | [Expected] | [On Track/Behind] |
| Services contributed to | [N] | [Expected] | [On Track/Behind] |

##### Onboarding Tasks
| Category | Total | Completed | Overdue | Blocked |
|----------|-------|-----------|---------|---------|
| Setup & Access | [N] | [N] | [N] | [N] |
| Training | [N] | [N] | [N] | [N] |
| Meet & Greet | [N] | [N] | [N] | [N] |
| Technical Ramp | [N] | [N] | [N] | [N] |

##### Check-in Status
| Type | Scheduled | Completed | Last One | Next One |
|------|-----------|-----------|----------|----------|
| Manager 1:1 | [Frequency] | [N] | [Date] | [Date] |
| Buddy check-in | [Frequency] | [N] | [Date] | [Date] |
| Skip-level | 1 (by day 30) | [Done/Pending] | [Date] | [Date] |

##### Signals & Notes
- **Positive:** [Good signals observed]
- **Concerns:** [Any concerns or areas needing support]
- **Buddy Feedback:** [Summary of buddy observations]

[Repeat for each new hire]

### Onboarding Health Metrics
| Metric | Current Cohort | Previous Cohort | Target |
|--------|---------------|-----------------|--------|
| Avg days to first CR | [X] | [Y] | <14 |
| Avg days to first merge | [X] | [Y] | <21 |
| Training completion rate (by day 30) | [X]% | [Y]% | 100% |
| Buddy satisfaction | [X/5] | [Y/5] | >4/5 |
| New hire satisfaction | [X/5] | [Y/5] | >4/5 |

### Blocked Onboarding Items
| New Hire | Blocked Task | Blocker | Days Blocked | Resolution |
|----------|-------------|---------|--------------|-----------|

### Upcoming Milestones (Next 2 Weeks)
| New Hire | Milestone | Target Date | Readiness | Support Needed |
|----------|-----------|-------------|-----------|----------------|

### Recommended Manager Actions
1. [Specific action: e.g., "Schedule 30-day check-in with Alice for next Thursday"]
2. [Specific action: e.g., "Bob's buddy hasn't met with him in 2 weeks - follow up"]
3. [Specific action: e.g., "Carol is ahead of schedule - consider assigning stretch project"]

### 30/60/90 Day Reviews Due
| New Hire | Review Type | Due Date | Prep Needed |
|----------|------------|----------|-------------|
```

## Delivery
Send the full report as a Slack DM to me every Monday. Send immediate alerts if a new hire has not created their first CR by day 21, if buddy check-ins have been missed for 2+ weeks, or if any onboarding blocker remains unresolved for more than 5 days.
