# Escalation Daily Check

Run a daily escalation health check for my team. Do ALL of the following:

## 1. Active Escalations Status

Check for any active escalations involving my team:
- ES2 escalations currently open
- Any KCR-Lite, KCR, KCR-Focus, or KCI tickets where my engineers are involved
- C2R cases currently in progress
- Cases with customer sentiment trending YELLOW or RED

For each, provide:
- Case ID and customer
- Current temperature (Operational Impact / Business Sentiment)
- Days open
- Last update timestamp
- Assigned engineer
- Next action due

## 2. At-Risk Cases (Pre-Escalation)

Identify cases at risk of becoming escalations:
- Cases approaching or breaching FR-SLA
- Cases with no update in 48+ hours (languishing)
- Cases with multiple customer follow-ups (frustration signal)
- High-sev cases (Sev-1/Sev-5) that are aging
- Cases where customer has requested escalation or expressed dissatisfaction

## 3. KCR/KCI Pipeline Review

Check KCR/KCI status:
- Any new KCRs filed in last 24 hours involving our customers
- KCR temperature changes (movement toward RED)
- Get-to-Green plan updates due today
- KCIs scheduled for WBR this week

## 4. Escalation Trend Analysis

Review patterns:
- Number of escalations this week vs last week
- Repeat customers appearing in escalations
- Common services or issue types triggering escalations
- Time-to-resolution trends for closed escalations

## 5. Action Items

Generate prioritized action list:
- 🔴 Immediate: Active KCIs, RED temperature cases, SLA breaches
- 🟡 Today: Aging escalations, Get-to-Green updates due, customer follow-ups needed
- 🟢 This week: KCR-Lite monitoring, trend concerns, prevention actions

---

Send as consolidated Slack DM with clear sections. Flag anything requiring my immediate intervention at the top.
