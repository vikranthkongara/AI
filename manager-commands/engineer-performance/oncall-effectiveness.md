# Oncall Effectiveness Report

Generate a per-engineer oncall effectiveness report covering the last oncall rotation cycle (default: past 2 weeks). This helps identify engineers who may need oncall coaching, recognize strong performers, and spot systemic issues with alert quality.

## Data Sources
- Oncall system: rotation schedules, pages received, acknowledgment timestamps, resolution timestamps, escalation records
- Taskei: oncall-related tickets created, runbook contribution tasks
- CRUX CRs: commits to runbook repositories, monitoring/alerting changes
- Slack: oncall channel activity and handoff notes

## Instructions

1. Query the oncall system for the team's most recent completed rotation cycle. Identify each engineer who was on primary or secondary oncall.

2. For each engineer on rotation, collect:
   - Total number of pages/alerts received during their shift
   - Time to acknowledge each page (median and p95)
   - Time to resolve each page (median and p95)
   - Number of escalations made (to secondary, to other teams, to management)
   - Number of pages that were noise/false positives (auto-resolved or immediately closed)
   - After-hours vs business-hours page distribution

3. Query CRUX CRs for any runbook updates, monitoring improvements, or alert tuning changes authored by each engineer during or immediately after their rotation (within 3 business days).

4. Check Taskei for:
   - Follow-up tickets created from oncall issues
   - Runbook improvement tasks filed or completed
   - Any COE/postmortem action items assigned and completed

5. Calculate effectiveness metrics:
   - Acknowledgment rate (% acknowledged within SLA, typically 5 minutes)
   - Resolution efficiency (median time to resolve vs team average)
   - Escalation rate (% of pages escalated vs handled independently)
   - Follow-through score (% of oncall issues that got follow-up tickets)
   - Improvement contributions (runbook updates, alert tuning CRs)

6. Identify patterns:
   - Engineers with consistently high escalation rates (may need coaching)
   - Engineers who proactively improve runbooks after rotation (recognize them)
   - Repeat alerts that hit multiple rotations (systemic issues to fix)
   - Time-of-day patterns suggesting alert tuning opportunities

## Output Format

```
## Oncall Effectiveness Report
**Period:** [start date] - [end date]
**Team:** [team name]

### Per-Engineer Summary

| Engineer | Pages | Median Ack | Median Resolve | Escalation Rate | Follow-ups Filed | Runbook Updates |
|----------|-------|-----------|----------------|-----------------|------------------|-----------------|
| [name]   | [n]   | [time]    | [time]         | [%]             | [n]              | [n CRs]         |

### Highlights
- **Strong performers:** [engineers with fast resolution, low escalation, proactive improvements]
- **Coaching opportunities:** [engineers with high escalation rates or slow acknowledgment - frame constructively]
- **Systemic issues:** [repeated alerts, noisy services, missing runbooks]

### Alert Quality
- Total pages this cycle: [n]
- False positive rate: [%]
- Top noisy alerts: [list top 3 with suggested actions]

### Recommended Actions
1. [Specific action items based on findings]
2. [e.g., "Pair [engineer] with [senior] for next rotation"]
3. [e.g., "File ticket to tune [alert name] - fired [n] times with no action needed"]
```

## Delivery
Send the formatted report as a Slack DM to me. If any engineer has an acknowledgment rate below 80% or escalation rate above 50%, flag this at the top of the message with a note to schedule a 1:1 discussion (do not send this data to anyone else).
