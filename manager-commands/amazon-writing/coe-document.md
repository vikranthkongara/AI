# Correction of Error (COE) Document

Generate a COE document with 5 Whys root cause analysis, timeline reconstruction, contributing factors, and action items with owners.

## Data Sources
- Oncall: incident ticket, pages received, timeline from monitoring tools, runbook actions taken
- Pipelines: recent deployments that may have triggered the issue
- Apollo: deployment logs, rollback history, configuration changes
- Internal search: related past COEs, service architecture docs
- CRs: code changes deployed in the incident window
- Slack/Email: incident channel communications, customer reports, escalation threads
- Calendar: change freeze windows, on-call rotation at time of incident

## Instructions
1. **Executive summary (2-3 sentences).** What happened, when, customer impact, current status. No opinions -- just facts.
2. **Timeline of events.** Minute-by-minute reconstruction from first signal to full resolution. Include:
   - When the issue started (or when we believe it started)
   - When it was detected (and how: alarm, customer report, manual observation)
   - Key actions taken and by whom
   - When it was mitigated vs fully resolved
3. **Customer impact.** Quantify precisely: number of customers affected, duration of impact, error rates during incident, any data loss or corruption, SLA implications.
4. **Root cause (5 Whys).** Work backwards from the symptom:
   - Why did the customer see an error? Because X.
   - Why did X happen? Because Y.
   - Continue until you reach the systemic root cause (usually a process, tooling, or design gap -- not a human mistake).
5. **Contributing factors.** What conditions made this possible or made detection/resolution slower? (e.g., missing alarms, unclear runbook, single point of failure, insufficient testing)
6. **Action items.** For each: description, owner, priority (P0/P1/P2), due date, verification method. Action items must address root cause and contributing factors, not just symptoms.
7. **Lessons learned.** What did we learn that applies beyond this specific incident? What mechanisms should we build?

### Amazon Writing Style Rules
- Facts, not blame: "The deployment at 14:32 UTC introduced a regression" not "Engineer X made a mistake"
- Specific times: always UTC, always precise (14:32 not "around 2:30 PM")
- Quantified impact: "4,237 customers received 500 errors over 47 minutes" not "many customers were affected"
- No weasel words: "inadequate monitoring" must become "no alarm existed for the cache eviction rate metric, which exceeded 90% during the incident"
- Action items must be SMART: specific, measurable, with an owner and a date
- Root cause must be systemic: if your 5 Whys ends at "human error", go deeper -- what system allowed the error to reach production?

## Output Format
```
[Title: COE - <Brief Description> - <Date>]
[Severity: SEV-X] [Duration: Xh Ym] [Customers Impacted: N]

Executive Summary
[2-3 sentences: what, when, impact, status]

Timeline
| Time (UTC) | Event |
|------------|-------|
| HH:MM      | ...   |

Customer Impact
[1-2 paragraphs with precise quantification]

Root Cause Analysis (5 Whys)
1. Why [symptom]? Because [cause 1].
2. Why [cause 1]? Because [cause 2].
3. Why [cause 2]? Because [cause 3].
4. Why [cause 3]? Because [cause 4].
5. Why [cause 4]? Because [root cause].

Root Cause: [One sentence systemic root cause]

Contributing Factors
- [Factor 1: description and how it contributed]
- [Factor 2: description and how it contributed]

Action Items
| # | Action | Owner | Priority | Due Date | Verification |
|---|--------|-------|----------|----------|--------------|
| 1 | ...    | ...   | P0/P1/P2 | ...      | ...          |

Lessons Learned
[1-2 paragraphs on broader applicability]
```

## Delivery
Save as draft document. Send Slack DM with link to incident owner and manager. If there is a COE review meeting on the calendar, attach to the invite.
