# Customer Escalation Paths Overview

Quick reference for all AWS Support escalation paths. Evaluate top-to-bottom — the first matching path determines the outcome.

## Decision Tree

| # | Path | When to Use | SLA |
|---|------|-------------|-----|
| 1 | **C2IE** | Catastrophic incident, production hard down, severe financial impact, 24x7 all-hands needed | Immediate |
| 2 | **C2R** | Sev-5 critical case, Support Engineering handles via Contact to Resolution | Hourly updates |
| 3 | **ES2** | Case needs faster resolution or service team action. First encourage Live Contact, then escalate via Command Center | Varies by priority |
| 4 | **SE Fast Track** | ES2 raised but case still stalled. Engages Escalation Core Team + SE for sustained traction | P1: ~2hr, P2: ~4hr, P3: ~6hr, P4: ~8hr |
| 5 | **GME** | ES2 + Fast Track exhausted. Email to L8 Service GM + GM's manager | 24-48hr |
| 6 | **KCR / KCI** | Temperature matrix outcome (see below) | Ongoing |
| 7 | **KCR-Lite** | Below KCR threshold but worth proactive tracking | Ongoing |
| 8 | **Concierge** | Billing or accounts receivable issue | Case-based |
| 9 | **CECP** | Active Large Scale Event affecting customer | Event-driven |
| 10 | **Leadership Engagement** | Customer trust in AWS Support eroded, request SE leadership call | As needed |

## Standard Escalation Flow

```
Case → ES2 → GME → KCR → KCI
```

Everything must start with a customer case. Do not make a TT/SIM without a case.

## When NOT to Escalate to ES2

- TT is not actually languishing (>5 days without meaningful update) and no impact provided
- Escalation is preemptive — SE is actively engaged and doesn't need ST
- Escalation is for monitoring only (ask should be tangible, tied to deliverable)
- Technical issue tied to known bug already being addressed by ST
- Issue related to an active LSE
- Escalation is for a feature request

## Before Escalating — Try Live Contact First

Enterprise customers can reach Support 24/7 via Live Contact for urgent issues. Always encourage the customer to initiate a Live Contact (chat or call) from Support Center before escalating to ES2.

---

## Key Contacts

- **ES2 Escalations Team**: Primary escalation management
- **E2M On-Call**: Directory at https://w.amazon.com/bin/view/E2M/External/Oncalls/
- **Command Center**: https://command-center.support.aws.a2z.com/supportDashboard#/oncalls
- **TAM Escalation Email**: aws-tam-escalation@amazon.com
- **Slack**: #escalation

## Key Wikis

- TAM Escalation Field Guide: https://w.amazon.com/bin/view/AWS/Teams/TAM/Escalation/FieldGuide/
- ES2 Escalation Process: https://w.amazon.com/bin/view/E2M/External/Escalations/
- C2IE Wiki: https://w.amazon.com/bin/view/C2IE/
- KCR/KCI Wiki: https://w.amazon.com/bin/view/AWS/Teams/TAM/Escalation/KCR-KCI/

## Acronyms

| Acronym | Meaning |
|---------|---------|
| C2IE | Critical Customer Incident Escalation |
| C2R | Contact to Resolution |
| E2M | Escalation and Event Management (also ES2) |
| ES2 | Escalation Support 2 (also E2M) |
| ESM | Enterprise Support Manager |
| GME | General Manager Escalation |
| KCI | Key Customer Issue |
| KCR | Key Customer Risk |
| LSE | Large Scale Event |
| RCA | Root Cause Analysis |
| TAM | Technical Account Manager |
