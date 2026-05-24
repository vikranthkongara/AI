# KCR (Key Customer Risk) Playbook

## What is a KCR?

The KCR process identifies, tracks, and gets help on situations that impact a customer's ability to use AWS or negatively impact customer sentiment. It provides visibility and engagement to drive a successful outcome. KCRs may advance to KCI.

**Rule of thumb**: If you think your customer may have a KCR, they probably do — go ahead and create one.

## KCR Tiers (Lowest to Highest)

1. **KCR-Lite** — Below KCR threshold but worth proactive tracking
2. **KCR** — Standard Key Customer Risk
3. **KCR-Focus** — Intermediate stage requiring time or Support leader review before potential KCI
4. **KCI** — Key Customer Issue (presented at AWS WBR)

## KCR Criteria — When to Declare

1. **Already Escalated** — Issue already escalated to service GM or team lead. It's serious and should be tracked.
2. **Not Getting Traction** — You've been engaged but it's not moving quickly enough. Needs escalation to service owner.
3. **Slow Burns** — Customer not shouting but lack of progress is eroding trust. Needs acceleration.
4. **Paper Cuts** — Seemingly small but repeating issues eroding customer trust.
5. **Visibility** — "I wish you would have told me about that before."
6. **Risk of Missed Customer Commitment** — Customer given a date from AWS for service/feature/fix and evidence we'll break that promise.

## Temperature Matrix

Cross-reference **Operational Impact** (rows) with **Business Sentiment** (columns):

| Impact ↓ / Sentiment → | GREEN | BLUE | YELLOW | RED |
|-------------------------|-------|------|--------|-----|
| **GREEN** | No KCR | No KCR | KCR-Lite | KCR |
| **BLUE** | No KCR | KCR-Lite | KCR | KCR-Focus |
| **YELLOW** | KCR-Lite | KCR | KCR-Focus | KCI |
| **RED** | KCR | KCR-Focus | KCI | KCI |

### Operational Impact Temperatures

- **GREEN**: Minimal/no impact, workaround available, non-production
- **BLUE**: Moderate impact, degraded but functional, partial workaround
- **YELLOW**: Significant impact, production affected, limited workaround
- **RED**: Severe/catastrophic, production hard down, no workaround, significant revenue impact

### Business Sentiment Temperatures

- **GREEN**: Customer satisfied, normal engagement
- **BLUE**: Mild frustration, trust slightly strained
- **YELLOW**: Customer expressing dissatisfaction, trust declining, threatening churn or executive attention
- **RED**: Customer actively considering migration, executive complaints, media/social risk, legal threats

## Notification Matrix

| Level | To | CC | Slack Required? |
|-------|----|----|-----------------|
| KCR-Lite | Account Team | ESM | No |
| KCR | Account Team | ESM, Sr ESM | No |
| KCR-Focus | Account Team + Managers, AM/SA LoL | ESM, Sr ESM | Yes |
| KCI | Account Team + Managers, AM/SA LoL, AM/SA Director | ESM, Sr ESM, ES Director | Yes |

## KCR Process Steps

1. **Identify** — Assess using criteria and temperature matrix above
2. **Create** — File KCR via https://kci.corp.amazon.com
3. **Get-to-Green Plan** — Develop action plan addressing:
   - Technical fix/resolution
   - Customer relationship repair
   - Timeline and milestones
4. **Drive Updates** — Regular cadence updates on progress
5. **Review** — Support leadership reviews for potential KCI elevation
6. **Close** — When customer is back to GREEN/GREEN on temperature matrix

## Important Notes

- KCRs may be about issues NOT caused by AWS (partners, third parties, customers themselves)
- A KCR on path to resolution can STILL go to KCI — misconception that it won't
- KCRs focus on customer experience, not a particular bug
- Get-to-Green includes fixing technical issues AND repairing customer relationship
- KCRs may stay open after technical solutions deployed until sentiment recovers
- Any customer, regardless of size and spend, can be taken to KCR/KCI

## Tools

- **KCI.CORP**: https://kci.corp.amazon.com — KCR/KCI web tool
- **KCR Expert PartyRock**: https://internal.partyrock.aws.dev/u/glackinj/-6RJasDm2/KCR-Expert
- **Granular Paging**: For urgent escalation notifications
