# Promotion Readiness Assessment

Compile evidence for promotion cases by gathering quantitative and qualitative data about an engineer's scope of work, impact metrics, leadership examples, and cross-team influence. This creates a data-driven foundation for promotion documents.

## Data Sources
- CRUX CRs: code contributions, review activity, cross-team reviews
- Taskei: project ownership, task complexity, leadership of initiatives
- Pipelines: services owned, deployment frequency, operational maturity
- Apollo: deployment scope and responsibility
- Oncall system: incident leadership, escalation handling, operational improvements
- Calendar: meetings led, cross-team collaborations, mentoring sessions
- Slack: cross-team communication, technical leadership signals
- Email (Outlook): stakeholder communications, project updates authored

## Instructions

**Note:** Run this for a specific engineer. Default to gathering data for the past 6 months unless a different period is specified.

1. **Scope of Work** - Query Taskei and CRUX CRs to establish:
   - Number and complexity of projects led vs contributed to
   - Services/systems owned or significantly architected
   - Lines of code contributed (as a directional signal, not absolute measure)
   - Number of CRs authored and their average size/complexity
   - Cross-package and cross-service changes (breadth indicator)
   - Design documents authored (indicates senior-level thinking)

2. **Impact Metrics** - Gather quantifiable impact:
   - Features shipped and their business metrics (if available in Taskei ticket descriptions)
   - Operational improvements: latency reduced, error rates lowered, costs saved
   - System reliability improvements: pages reduced, availability increased
   - Developer productivity improvements: build time reduced, test time improved
   - Incidents prevented through proactive work

3. **Technical Leadership** - Identify leadership signals:
   - Design docs authored and approved (especially multi-team scope)
   - CRs reviewed for other teams (cross-team influence)
   - Technical decisions made (architecture choices documented in CRs/docs)
   - Complex problems solved (incident resolution, debugging)
   - Code review quality (teaching comments, architectural guidance)
   - Standards/patterns established that others adopted

4. **Cross-team Influence** - Track broader organizational impact:
   - CRs reviewed or authored in other teams' packages
   - Slack messages in cross-team channels providing guidance
   - Meetings with other teams (calendar data)
   - Shared libraries or tools created/maintained
   - Presentations given to broader org

5. **Mentoring and Growing Others** - Gather evidence:
   - CR review coaching (per mentoring-activity report)
   - Onboarding buddy work
   - Knowledge sharing sessions led
   - Engineers they have helped ramp up

6. **Operational Excellence** - Track operational maturity:
   - Oncall performance metrics
   - Runbook contributions
   - Incident leadership (driving resolution vs escalating)
   - Monitoring and alerting improvements
   - Operational reviews led

7. **Gap Analysis** - Identify what might be missing for the target level:
   - Compare activities against the next-level expectations
   - Note areas where more evidence is needed
   - Suggest activities to close gaps before promo submission

## Output Format

```
## Promotion Readiness Assessment
**Engineer:** [name]
**Current Level:** [L]
**Target Level:** [L+1]
**Assessment Period:** [start] - [end]
**Assessment Date:** [today]

---

### Executive Summary
[2-3 sentence summary: Is this engineer ready? What's their strongest dimension? What's the biggest gap?]

**Overall Readiness:** [Ready / Nearly Ready - 1-2 gaps / Not Yet - significant gaps]

---

### 1. Scope of Work
**Rating:** [Exceeds target level / Meets target level / Below target level]

- Projects led: [n] ([list key projects with brief descriptions])
- Services owned: [list]
- Design documents authored: [n] ([list with links])
- Cross-service changes: [n] CRs touching [n] different services
- Key accomplishment: [single most impressive scope example]

### 2. Impact Metrics
**Rating:** [Exceeds / Meets / Below]

| Metric | Before | After | Impact |
|--------|--------|-------|--------|
| [e.g., API latency] | [value] | [value] | [% improvement] |
| [e.g., Error rate] | [value] | [value] | [% reduction] |
| [e.g., Cost] | [value] | [value] | [$ saved] |

- Key impact story: [strongest example with numbers]

### 3. Technical Leadership
**Rating:** [Exceeds / Meets / Below]

- Architecture decisions: [list key decisions and outcomes]
- Technical standards set: [patterns/practices introduced]
- Complex problems solved: [list with brief context]
- Design doc quality: [assessment based on review feedback]

### 4. Cross-team Influence
**Rating:** [Exceeds / Meets / Below]

- Teams collaborated with: [list]
- Shared tools/libraries: [list]
- Cross-team CRs: [n] reviews given to other teams
- Org-wide contributions: [presentations, shared tooling, etc.]

### 5. Mentoring & Growing Others
**Rating:** [Exceeds / Meets / Below]

- Engineers mentored: [list with outcomes]
- Knowledge shares given: [n] ([topics])
- CR coaching examples: [n] teaching comments, [highlights]
- Team capability improvements: [what the team can do now because of this person]

### 6. Operational Excellence
**Rating:** [Exceeds / Meets / Below]

- Oncall metrics: [summary from oncall-effectiveness data]
- Incidents led: [n] with [outcomes]
- Operational improvements: [list]
- Runbook/monitoring contributions: [n]

---

### Gap Analysis for [Target Level]

| Dimension | Status | Gap | Suggested Action |
|-----------|--------|-----|------------------|
| [dimension] | [green/yellow/red] | [what's missing] | [what to do] |

### Recommended Timeline
- **If Ready:** Submit in next promo cycle ([date])
- **If Gaps:** [n] months to close gaps, target [future cycle date]
- **Key actions before submission:**
  1. [specific action]
  2. [specific action]
  3. [specific action]

### Promo Doc Starter (Key Bullets)
- [Ready-to-use bullet point for promo doc]
- [Ready-to-use bullet point for promo doc]
- [Ready-to-use bullet point for promo doc]
- [Ready-to-use bullet point for promo doc]
- [Ready-to-use bullet point for promo doc]
```

## Delivery
Send the formatted report as a Slack DM to me. This is highly confidential and must not be shared with the engineer or anyone else. I will use this as input for writing the official promotion document and for coaching conversations.
