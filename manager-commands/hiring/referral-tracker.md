# Referral Tracker

Track team referral submissions: where referrals are in the pipeline, conversion rates, and encourage referral activity.

## Data Sources
- Email/Outlook (referral submission confirmations, status updates from recruiting)
- Taskei (referral tracking tasks, if maintained)
- Slack DMs (recruiter updates on referral status)
- Calendar (referral-related events, hiring happy hours)

## Instructions
1. Check email for all referral-related communications from the past 90 days. For each referral, track:
   - Referring team member
   - Candidate name (or anonymized identifier)
   - Role referred for
   - Submission date
   - Current status in pipeline
   - Last status update date
2. Map each referral through the pipeline stages:
   - Submitted (referral received by recruiting)
   - Recruiter Review (being evaluated for fit)
   - Phone Screen (actively interviewing)
   - Loop Scheduled/Completed
   - Debrief
   - Offer
   - Accepted/Declined/Rejected
3. Calculate referral metrics:
   - Total referrals submitted (by team member and overall)
   - Conversion rate at each stage
   - Overall referral-to-hire rate
   - Average time from referral to decision
   - Compare referral conversion rate to non-referral pipeline
4. Identify stale referrals:
   - Referrals submitted > 2 weeks ago with no status update
   - Referrals where the candidate has not been contacted
   - Referrals stuck at a stage without movement
5. Identify team referral patterns:
   - Who is referring most actively?
   - Who hasn't submitted referrals recently? (opportunity for encouragement)
   - Which roles are getting the most referrals?
   - Roles with zero referrals (may need specific asks)
6. Check for referral bonus eligibility:
   - Referrals that resulted in hires
   - Bonus processing status
   - Upcoming milestones for bonus payout
7. Generate talking points for encouraging more referrals (based on open roles and gaps).

## Output Format
```
## Referral Tracker Report
**Date:** [Date]
**Period:** Last 90 days
**Total Referrals Submitted:** [N]
**Referrals Converted to Hire:** [N]
**Conversion Rate:** [X]%

### Pipeline Status
| Stage | Count | Avg Days in Stage | Stale (>2 weeks no update) |
|-------|-------|-------------------|---------------------------|
| Submitted | [N] | [X] | [N] |
| Recruiter Review | [N] | [X] | [N] |
| Phone Screen | [N] | [X] | [N] |
| Loop | [N] | [X] | [N] |
| Offer | [N] | [X] | [N] |
| Hired | [N] | - | - |
| Rejected/Declined | [N] | - | - |

### Active Referrals Detail
| Referrer | Candidate | Role | Submitted | Current Stage | Days in Stage | Last Update |
|----------|-----------|------|-----------|---------------|---------------|-------------|

### Referral Activity by Team Member
| Team Member | Referrals (90d) | In Pipeline | Converted | Rate | Last Referral |
|-------------|----------------|-------------|-----------|------|---------------|
[Sorted by activity]

### Conversion Funnel
| Stage Transition | Referrals | Non-Referrals | Referral Advantage |
|-----------------|-----------|---------------|-------------------|
| Submit -> Screen | [X]% | [Y]% | [+/-Z]% |
| Screen -> Loop | [X]% | [Y]% | [+/-Z]% |
| Loop -> Offer | [X]% | [Y]% | [+/-Z]% |
| Offer -> Accept | [X]% | [Y]% | [+/-Z]% |
| **End-to-end** | [X]% | [Y]% | [+/-Z]% |

### Stale Referrals (Need Follow-Up)
| Referrer | Candidate | Role | Submitted | Stage | Days Without Update | Action Needed |
|----------|-----------|------|-----------|-------|--------------------|--------------| 

### Referral Gaps (Roles with Zero Referrals)
| Role | Level | Days Open | Ideal Candidate Profile | Suggested Ask |
|------|-------|-----------|------------------------|---------------|

### Bonus Tracking
| Referrer | Candidate | Hire Date | Bonus Amount | Payout Date | Status |
|----------|-----------|-----------|-------------|-------------|--------|

### Team Referral Engagement
- Active referrers (submitted in last 30d): [N]/[Team Size]
- Team members with no referrals this quarter: [Names]
- Top referrer: [Name] ([N] referrals, [N] converted)

### Suggested Referral Asks for Team
Based on open roles and pipeline gaps:
1. **[Role]:** Looking for [brief profile]. [Name] and [Name] may have relevant networks from [context].
2. **[Role]:** Specifically need [skill]. Consider reaching out to [suggested source/community].

### Recommendations
1. [Follow up on stale referrals with recruiting]
2. [Encourage specific team members to refer for specific roles]
3. [Celebrate recent referral hires to motivate more referrals]
```

## Delivery
Send the full report as a Slack DM to me every other Monday. Send immediate alerts when a referral converts to a hire (so I can recognize the referrer) or when a referral has been stuck without an update for more than 3 weeks.
