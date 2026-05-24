# Engineer Workload Assessment

Assess an individual engineer's current workload across all dimensions to identify overload risk and ensure sustainable pace.

## Data Sources
- Taskei: Active tasks, task count, story points assigned, sprint commitments
- CRUX CRs: Open CRs awaiting review, CRs in-flight authored, review requests pending
- Oncall system: Current or upcoming oncall shifts, recent page volume during their shifts
- Calendar: Meeting load, focus time availability, interview loops scheduled
- Slack: Activity hours (early morning/late night signals), urgent requests volume
- Pipelines: Active deployments they're responsible for
- Apollo: Services they own with active issues

## Instructions
1. Query Taskei for all tasks currently assigned to {{ENGINEER_NAME}}:
   - Count active in-progress tasks (should be 1-3 max for healthy WIP)
   - Count total assigned tasks including backlog
   - Check for tasks with approaching or missed deadlines
   - Identify any cross-team tasks adding coordination overhead
2. Check CRUX for CR load:
   - CRs they authored that are waiting for review (blocked on others)
   - CRs where they are requested as reviewer (demands on their time)
   - Average CR size they're producing (large CRs = high cognitive load)
3. Check oncall system:
   - Are they currently oncall or oncall in the next 7 days?
   - What was their page volume in their last oncall shift?
   - Any ongoing incidents they're shepherding?
4. Analyze calendar for the current and next week:
   - Total meeting hours per day
   - Longest block of uninterrupted focus time available
   - Interview loops scheduled (high cognitive cost)
   - Count recurring meetings
5. Check Slack activity patterns:
   - Messages sent outside core hours (8am-6pm) - burnout signal
   - Volume of urgent/time-sensitive requests directed at them
   - Are they being pulled into too many support threads?
6. Check Pipelines/Apollo:
   - Any active deployments in progress
   - Services with elevated error rates they need to monitor
7. Calculate a workload score across dimensions and flag if overloaded.

## Output Format
```
## Workload Assessment: {{ENGINEER_NAME}}
### Date: {{DATE}}
### Overall Load: [Light / Moderate / Heavy / OVERLOADED]

### Task Load
- Active in-progress tasks: [count] (healthy: 1-3)
- Total assigned tasks: [count]
- Tasks with approaching deadlines (< 3 days): [count]
- Blocked tasks: [count]
- Cross-team coordination tasks: [count]

### Code Review Load
- Authored CRs awaiting review: [count]
- Pending review requests on them: [count]
- Average CR size (lines): [count]

### Oncall & Operational Load
- Oncall status: [On/Off/Upcoming in X days]
- Last shift page count: [count]
- Active incidents owned: [count]

### Meeting & Calendar Load
- Meeting hours this week: [X] / 40 available
- Longest focus block: [X hours]
- Interview loops this week: [count]
- Focus time ratio: [X%] (healthy: >50%)

### Burnout Signals
- After-hours Slack activity: [None / Low / Moderate / High]
- Weekend activity: [Yes/No]
- Velocity trend: [Stable / Declining / Improving]

### Risk Assessment
| Dimension | Score (1-5) | Notes |
|-----------|-------------|-------|
| Task volume | ... | ... |
| CR load | ... | ... |
| Oncall burden | ... | ... |
| Meeting tax | ... | ... |
| After-hours work | ... | ... |
| **Total** | **X/25** | [Light<10, Moderate 10-15, Heavy 15-20, Overloaded>20] |

### Recommended Actions
- [Specific actions: redistribute work, cancel meetings, defer reviews, etc.]
```

## Delivery
Send as a Slack DM to me. If overall load is OVERLOADED, mark the message as urgent.
