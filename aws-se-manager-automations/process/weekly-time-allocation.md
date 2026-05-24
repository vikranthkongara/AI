# Weekly Team Time Allocation Estimate

Estimate how the team collectively spent their time this week across different work categories to identify imbalances and inform planning.

## Data Sources
- Taskei: Tasks worked on, categories, story points consumed
- CRUX CRs: Code review time (authoring and reviewing), type of work (feature, bug fix, ops)
- Calendar: Meeting hours, interview loops, team ceremonies
- Oncall system: Time spent on incidents, operational work
- Pipelines: Deployment time and attention required
- Slack: Support requests handled, cross-team coordination time

## Instructions
1. **Feature Development Time**:
   - Check Taskei for tasks in "feature" or "project" categories worked on this week
   - Check CRUX CRs tagged as feature work or linked to feature tasks
   - Estimate hours based on CR size and task progress
2. **Operational Work**:
   - Check oncall system: incidents handled, time to resolve, follow-up work
   - Check for operational tasks in Taskei (monitoring, alerts, maintenance)
   - Check CRs that are operational fixes (not planned feature work)
   - Include deployment monitoring time from Pipelines
3. **Meetings & Ceremonies**:
   - Sum meeting hours for each team member from calendars
   - Categorize: team ceremonies, cross-team syncs, 1:1s, interviews, ad-hoc
4. **Interviews & Hiring**:
   - Check calendars for interview loops
   - Estimate prep + interview + debrief time per loop (typically 3-4 hours total)
5. **Tech Debt & Improvements**:
   - Check Taskei for tech debt tasks worked on
   - Check CRs categorized as refactoring or improvement
   - Include tooling improvements and automation work
6. **Learning & Development**:
   - Calendar events: training, reading groups, tech talks
   - Time spent on development plan activities
7. **Unplanned Work**:
   - Urgent requests that weren't in the sprint plan
   - Ad-hoc support for other teams
   - Context switching overhead estimate
8. **Calculate Team Totals and Per-Person Averages**:
   - Total available hours: [team size] x 40
   - Subtract PTO and holidays
   - Map actual hours to categories
   - Compare to ideal allocation targets

## Output Format
```
## Weekly Time Allocation Report
### Team: {{TEAM_NAME}}
### Week: {{WEEK_OF}}
### Team Size: [X] engineers | Available Hours: [Y] (after PTO: [Z])

### Time Allocation Summary
| Category | Hours | % of Total | Target % | Delta |
|----------|-------|-----------|----------|-------|
| Feature development | ... | ...% | 50% | ... |
| Operational work | ... | ...% | 15% | ... |
| Meetings & ceremonies | ... | ...% | 15% | ... |
| Tech debt / improvements | ... | ...% | 10% | ... |
| Interviews & hiring | ... | ...% | 5% | ... |
| Learning & development | ... | ...% | 5% | ... |
| Unplanned / interrupt | ... | ...% | 0% (aspirational) | ... |

### Visual Breakdown
[Proportional bar or percentage representation]
Feature:    [====================] 45%
Ops:        [========]            20%
Meetings:   [======]              15%
Tech Debt:  [====]                10%
Interviews: [==]                   5%
Learning:   [=]                    3%
Unplanned:  [=]                    2%

### Per-Person Breakdown (Anonymized Ranges)
| Person | Feature % | Ops % | Meetings % | Notes |
|--------|-----------|-------|-----------|-------|
| Eng 1 | ...% | ...% | ...% | [Notable: heavy ops week] |
| Eng 2 | ...% | ...% | ...% | [Notable: interview heavy] |
| ... | ... | ... | ... | ... |

### Key Observations
- **Feature velocity this week**: [Higher/Lower/Same as last week] because [reason]
- **Ops burden**: [Expected/Elevated/Critical] - driven by [cause]
- **Meeting tax**: [Acceptable/High] - [X hours] could potentially be reclaimed
- **Unplanned work**: [None/Some/Significant] - came from [source]

### Week-over-Week Trend
| Category | 4 Wks Ago | 3 Wks Ago | 2 Wks Ago | Last Wk | This Wk |
|----------|-----------|-----------|-----------|---------|---------|
| Feature | ...% | ...% | ...% | ...% | ...% |
| Ops | ...% | ...% | ...% | ...% | ...% |
| Meetings | ...% | ...% | ...% | ...% | ...% |

### Imbalances to Address
- [If ops is too high]: Root cause and mitigation plan
- [If meetings are too high]: Specific meetings to cut
- [If feature work is too low]: What's crowding it out

### Recommendations for Next Week
1. [Specific action to improve allocation]
2. [Specific action to protect engineering time]
```

## Delivery
Send as a Slack DM to me every Friday at 4:00 PM to inform my weekend reflection and Monday planning.
