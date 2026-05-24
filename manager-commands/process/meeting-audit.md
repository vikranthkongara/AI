# Calendar & Meeting Audit

Analyze my calendar to identify meeting overload, inefficiencies, and opportunities to reclaim time for strategic work and team support.

## Data Sources
- Calendar: All meetings in the last 2 weeks and upcoming 2 weeks
- Slack: Async alternatives that could replace meetings, meeting-related complaints
- Email (Outlook): Meeting invites received, agendas (or lack thereof)

## Instructions
1. **Meeting Volume Analysis** (last 2 complete weeks):
   - Count total meeting hours per week
   - Count total number of meetings per week
   - Calculate percentage of working hours (40h) spent in meetings
   - Identify days with >6 hours of meetings (unsustainable)
   - Identify longest meeting-free block each day
2. **Meeting Categorization**:
   - Categorize every recurring meeting:
     - 1:1s with direct reports (essential)
     - 1:1 with my manager (essential)
     - Team ceremonies (standup, retro, planning - essential)
     - Cross-team syncs (evaluate necessity)
     - Informational meetings (could be email/doc)
     - Decision meetings (high value if well-run)
     - Status updates (often async-able)
     - Interview loops (necessary but schedulable)
   - Flag meetings without agendas in the invite
   - Flag meetings with >8 attendees (likely inefficient)
   - Flag meetings where I'm optional but attending
3. **Recurring Meeting Health Check**:
   - For each recurring meeting, assess:
     - Does it have a clear purpose and agenda?
     - Does it consistently start/end on time?
     - Could the outcome be achieved async (Slack/doc)?
     - Am I the right person to attend, or could I delegate?
     - When was it last evaluated for necessity?
4. **Focus Time Assessment**:
   - How much uninterrupted time (2+ hour blocks) do I have per week?
   - Is there protected time for: strategic thinking, writing, team support?
   - Compare focus time to recommended minimum (10+ hours/week for managers)
5. **Optimization Recommendations**:
   - Identify meetings to cancel, consolidate, shorten, or make async
   - Suggest schedule restructuring for better focus blocks
   - Recommend delegation opportunities

## Output Format
```
## Calendar Audit Report
### Period Analyzed: {{DATE_RANGE}}

### High-Level Stats
| Metric | Week 1 | Week 2 | Average |
|--------|--------|--------|---------|
| Total meeting hours | ... | ... | ... |
| Number of meetings | ... | ... | ... |
| % of time in meetings | ... | ... | ... |
| Focus blocks (2+ hrs) | ... | ... | ... |
| Days with 6+ hrs meetings | ... | ... | ... |

### Meeting Breakdown by Category
| Category | Hours/Week | Count | Essential? |
|----------|-----------|-------|------------|
| 1:1s (reports) | ... | ... | Yes |
| 1:1 (manager) | ... | ... | Yes |
| Team ceremonies | ... | ... | Yes |
| Cross-team syncs | ... | ... | Evaluate |
| Status updates | ... | ... | Likely async |
| Informational | ... | ... | Likely async |
| Interviews | ... | ... | Necessary |
| Other | ... | ... | Evaluate |

### Red Flags
- [ ] Meetings without agendas: [list]
- [ ] Meetings with 8+ attendees where I'm not critical: [list]
- [ ] Recurring meetings not evaluated in 3+ months: [list]
- [ ] Back-to-back meeting chains (no breaks): [instances]

### Optimization Recommendations
#### Cancel (save [X] hrs/week)
- [Meeting]: Reason it's not needed, alternative approach

#### Make Async (save [X] hrs/week)
- [Meeting]: Can be replaced with [Slack update/shared doc/email]

#### Shorten (save [X] hrs/week)
- [Meeting]: Currently [X] min, could be [Y] min because [reason]

#### Delegate (save [X] hrs/week)
- [Meeting]: [Team member] could attend instead because [reason]

#### Consolidate
- [Meeting A] + [Meeting B]: Could be combined because [overlap]

### Suggested Ideal Week Template
| Time | Mon | Tue | Wed | Thu | Fri |
|------|-----|-----|-----|-----|-----|
| AM | ... | ... | ... | ... | ... |
| PM | ... | ... | ... | ... | ... |

### Total Potential Time Savings: [X] hours/week
```

## Delivery
Send as a Slack DM to me on the first Monday of each month. Include action items I can take immediately (decline specific meetings, propose async alternatives).
