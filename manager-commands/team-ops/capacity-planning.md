# Sprint Capacity Planning Report

Calculate team capacity for the next sprint by factoring in PTO, oncall rotations, interview load, meetings overhead, and other commitments. This ensures realistic sprint planning and prevents over-commitment.

## Data Sources
- Calendar: PTO events, interview blocks, recurring meetings, oncall shifts
- Oncall system: upcoming rotation schedule
- Taskei: current sprint velocity, backlog size, carry-over tickets
- Slack: PTO announcements, schedule changes
- Email (Outlook): out-of-office auto-replies configured, PTO approvals

## Instructions

1. Determine sprint dates (next sprint start and end, typically 2 weeks).

2. For each team member, check Calendar and email for:
   - PTO days scheduled during the sprint (full days and half days)
   - Company holidays within the sprint
   - Pre-scheduled interviews (typically 1-hour debrief + 1-hour interview per loop)
   - Recurring meetings load (standups, sprint ceremonies, 1:1s, team meetings)
   - Training or conferences scheduled
   - On-site visits or travel days

3. Check oncall system for:
   - Who is on primary oncall during the sprint (reduce their capacity by 30-50%)
   - Who is on secondary/shadow oncall (reduce by 10-20%)
   - Handoff days (partial productivity loss)

4. Calculate per-engineer available capacity:
   - Start with total working hours in sprint (typically 10 days x 8 hours = 80 hours)
   - Subtract: PTO hours, holiday hours
   - Subtract: meeting overhead (count recurring calendar events)
   - Subtract: interview load (estimate 3 hours per interview loop)
   - Subtract: oncall tax (30% for primary, 15% for secondary)
   - Subtract: standard overhead (emails, Slack, context switching ~ 15%)
   - Result: effective coding/delivery hours

5. Convert to story points using team's historical velocity:
   - Calculate average story points per engineer-hour from last 3 sprints
   - Apply to available hours for capacity estimate

6. Compare against backlog:
   - Total story points in proposed sprint backlog
   - Carry-over from previous sprint
   - Buffer for unplanned work (typically 15-20%)

7. Flag risks:
   - Days where more than 50% of team is unavailable
   - Overlapping PTO that leaves critical services unowned
   - Oncall + PTO conflicts
   - Sprint at risk of over-commitment (backlog > capacity)

## Output Format

```
## Sprint Capacity Planning
**Sprint:** [sprint name/number]
**Dates:** [start] - [end]
**Working Days:** [n] (excluding holidays)

---

### Team Capacity Summary

| Engineer | Working Days | PTO | Oncall Tax | Interviews | Meetings | Effective Days | Story Points |
|----------|-------------|-----|-----------|------------|----------|----------------|--------------|
| [name]   | [n]         | [n] | [n days]  | [n loops]  | [n hrs]  | [n.n]          | [n]          |
| **TOTAL**| **[n]**     | **[n]** | **[n]** | **[n]**  | **[n]**  | **[n.n]**      | **[n]**      |

---

### Capacity Calculation

- **Gross team capacity:** [n] person-days
- **PTO reduction:** -[n] days ([names])
- **Oncall reduction:** -[n] days ([names on rotation])
- **Interview load:** -[n] days ([n] loops across team)
- **Meeting overhead:** -[n] days
- **Unplanned work buffer (20%):** -[n] days
- **Net available capacity:** [n] person-days = ~[n] story points

---

### Sprint Load vs Capacity

| Metric | Value | Status |
|--------|-------|--------|
| Proposed backlog | [n] SP | - |
| Carry-over | [n] SP | - |
| Total planned | [n] SP | - |
| Available capacity | [n] SP | - |
| Delta | [+/- n] SP | [Under-committed/Balanced/Over-committed] |

---

### Schedule Risks

| Date | Issue | Impact | Mitigation |
|------|-------|--------|------------|
| [date] | [e.g., "3/5 engineers on PTO"] | [coverage gap] | [suggestion] |
| [date] | [e.g., "Primary oncall + PTO overlap"] | [no backup] | [swap rotation] |

---

### Recommendations
1. [e.g., "Remove [n] SP from sprint to match capacity"]
2. [e.g., "Swap oncall rotation for [engineer] due to PTO conflict"]
3. [e.g., "Front-load critical path items before [date] when team shrinks"]
4. [e.g., "Interview load is [n] loops - consider asking recruiting to reduce for this sprint"]
```

## Delivery
Send the formatted report as a Slack DM to me at least 2 days before sprint planning. If the team is over-committed by more than 20%, highlight this prominently with a recommendation on what to cut or defer.
