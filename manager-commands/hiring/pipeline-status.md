# Hiring Pipeline Status

Provide a comprehensive view of the active hiring pipeline: open roles, candidates in process, upcoming interviews, pending offers, and bottlenecks.

## Data Sources
- Email/Outlook (recruiter communications, candidate updates, offer approvals)
- Calendar (scheduled interviews, debrief sessions, hiring meetings)
- Taskei (hiring-related tasks, role tracking)
- Slack DMs (recruiter and hiring coordinator messages)

## Instructions
1. Check email for recent recruiter communications to build the current pipeline state:
   - New candidates submitted for review
   - Phone screen results
   - On-site/virtual loop scheduled or completed
   - Debrief outcomes
   - Offer status updates (extended, accepted, declined, pending)
2. For each open role, compile:
   - Role title, level, and requisition ID
   - Date opened
   - Current candidates in pipeline (by stage)
   - Recruiter assigned
   - Status of job posting (active, paused, filled)
3. Check calendar for upcoming interview-related events:
   - Phone screens scheduled
   - Loop interviews this week and next
   - Debrief meetings scheduled
   - Hiring manager syncs
4. Track the funnel for each role:
   - Candidates sourced/applied
   - Phone screens conducted
   - Loops scheduled
   - Offers extended
   - Offers accepted
   - Calculate conversion rates at each stage
5. Identify pipeline bottlenecks:
   - Roles with no candidates in pipeline for > 2 weeks
   - Candidates stuck at a stage for > 1 week without movement
   - Debriefs not scheduled within 48 hours of loop completion
   - Offers pending approval for > 3 business days
6. Check for expiring or at-risk candidates:
   - Candidates with competing offers
   - Candidates who have been in process > 4 weeks
   - Top candidates where we need to move quickly
7. Calculate overall hiring velocity metrics.

## Output Format
```
## Hiring Pipeline Status
**Date:** [Date]
**Open Roles:** [N]
**Active Candidates:** [N]
**Offers Pending:** [N]

### Pipeline Summary
| Stage | Count | Avg Days in Stage | Target Days | Bottleneck? |
|-------|-------|-------------------|-------------|------------|
| Sourcing/Applied | [N] | [X] | <7 | [Y/N] |
| Recruiter Screen | [N] | [X] | <5 | [Y/N] |
| Phone Screen | [N] | [X] | <7 | [Y/N] |
| Loop Scheduled | [N] | [X] | <10 | [Y/N] |
| Loop Completed (Pending Debrief) | [N] | [X] | <3 | [Y/N] |
| Debrief Complete (Pending Decision) | [N] | [X] | <2 | [Y/N] |
| Offer Extended | [N] | [X] | <5 | [Y/N] |

### Open Roles Detail
#### [Role Title] - [Level] (Req: [ID])
- **Opened:** [Date] ([N] days ago)
- **Recruiter:** [Name]
- **Posting Status:** [Active/Paused]
- **Candidates in Pipeline:** [N]
  - Phone Screen: [N]
  - Loop Scheduled: [N]
  - Debrief Pending: [N]
  - Offer Stage: [N]
- **Conversion Rate:** [X]% (screen to offer)
- **Urgency:** [High/Medium/Low]
- **Notes:** [Any blockers or context]

[Repeat for each role]

### This Week's Interviews
| Date | Time | Candidate | Role | Type | Interviewers | Status |
|------|------|-----------|------|------|-------------|--------|

### Pending Debriefs
| Candidate | Role | Loop Date | Debrief Scheduled | Days Waiting |
|-----------|------|-----------|-------------------|-------------|

### Pending Offers
| Candidate | Role | Decision Date | Offer Status | Days Pending | Risk |
|-----------|------|--------------|--------------|-------------|------|

### At-Risk Candidates (Action Needed)
| Candidate | Role | Risk Factor | Recommended Action | Urgency |
|-----------|------|-------------|-------------------|---------|
| [Name] | [Role] | Competing offer | Expedite debrief | Immediate |
| [Name] | [Role] | In process > 4 weeks | Decision needed | High |

### Funnel Metrics (Last 90 Days)
| Role | Sourced | Screened | Looped | Offered | Accepted | Time to Fill |
|------|---------|----------|--------|---------|----------|-------------|

### Bottlenecks & Recommendations
1. [Bottleneck description] - [Recommended action]
2. [Bottleneck description] - [Recommended action]

### Upcoming Hiring Meetings
| Date | Type | Topic | Prep Needed |
|------|------|-------|-------------|
```

## Delivery
Send the full report as a Slack DM to me every Monday and Thursday morning. Send immediate alerts for at-risk candidates with competing offers or when a role has had no pipeline activity for 2+ weeks.
