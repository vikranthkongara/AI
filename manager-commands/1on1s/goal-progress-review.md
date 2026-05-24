# Individual Goal Progress Review

Check progress on individual goals set during the last review cycle, identify goals at risk, and suggest adjustments for the upcoming 1:1 discussion.

## Data Sources
- Taskei: Goals and OKRs set for the current cycle, associated tasks and their completion status
- CRUX CRs: Evidence of technical goals being pursued (new technologies adopted, design docs written)
- Pipelines: Delivery milestones hit for project-based goals
- Calendar: Learning activities, mentoring sessions, conference attendance for development goals
- Slack: Signals of goal-related activity or blockers raised
- Oncall system: Operational improvement goals progress

## Instructions
1. Retrieve {{ENGINEER_NAME}}'s goals for the current review cycle from Taskei. These should include both delivery goals and development goals.
2. For each delivery goal:
   - Check associated Taskei tasks: what percentage are complete vs. in-progress vs. not-started
   - Check Pipelines for any deployment milestones that map to the goal
   - Estimate completion likelihood given current velocity and time remaining in cycle
   - Flag as: On Track (>75% likely to complete), At Risk (50-75%), Behind (<50%)
3. For each development/growth goal:
   - Look for evidence of pursuit: learning activities on calendar, new technologies in CRs, mentoring relationships in Slack
   - Check if enabling conditions exist (stretch assignments available, learning time protected)
   - Assess whether the goal is still relevant or needs adjustment
4. For each goal flagged as At Risk or Behind:
   - Identify the root cause: scope creep, competing priorities, external blockers, unclear definition
   - Suggest specific adjustments: descope, extend timeline, add support, redefine success criteria
5. Calculate an overall goal health score for the engineer.

## Output Format
```
## Goal Progress Review: {{ENGINEER_NAME}}
### Review Cycle: {{CYCLE}} | Time Remaining: {{WEEKS}} weeks
### Overall Health: [X/Y goals on track]

### Delivery Goals
| # | Goal | Progress | Status | Risk Factor |
|---|------|----------|--------|-------------|
| 1 | ... | X% | On Track/At Risk/Behind | ... |
| 2 | ... | X% | On Track/At Risk/Behind | ... |

### Development Goals
| # | Goal | Evidence of Pursuit | Status | Notes |
|---|------|-------------------|--------|-------|
| 1 | ... | [What's been done] | ... | ... |
| 2 | ... | [What's been done] | ... | ... |

### Goals At Risk - Detailed Analysis
#### [Goal Name]
- **Current state**: [Where they are]
- **Root cause of risk**: [Why it's behind]
- **Suggested adjustment**: [What to propose in 1:1]
- **Support needed**: [What I can do to help]

### Recommended 1:1 Talking Points
1. Celebrate: [Goal that's going well - recognize effort]
2. Problem-solve: [Goal at risk - collaborative discussion]
3. Adjust: [Goal that may need redefining - check alignment]

### Action Items for Me (Manager)
- [Things I need to do to unblock or support their goals]
```

## Delivery
Send as a Slack DM to me 24 hours before our next scheduled 1:1 (check calendar for timing).
