# Resource Allocation Analysis

Analyze current team allocation across projects and initiatives to identify over-committed or under-utilized engineers and recommend rebalancing.

## Data Sources
- Taskei (task assignments, active sprints, project tags)
- CRUX CRs (which packages/services each engineer is actively reviewing or authoring)
- Calendar (meeting load per engineer, focus time availability)
- Oncall system (oncall rotation schedule, current oncall duties)
- Pipelines (deployment ownership indicating service responsibilities)

## Instructions
1. Query Taskei for all active tasks assigned to each team member. Group tasks by project/initiative.
2. For each engineer, calculate:
   - Number of active projects they are contributing to
   - Total story points assigned in the current sprint
   - Number of open CRs (authored and reviewing) from CRUX
   - Meeting load from calendar (hours per week in meetings)
   - Whether they are currently on oncall rotation
3. Identify over-committed engineers (signals):
   - Assigned to 3+ concurrent projects
   - Story points > 120% of team average
   - High CR review queue (> 5 pending reviews)
   - Meeting load > 40% of work hours
   - Currently oncall while also carrying full sprint load
4. Identify under-utilized engineers (signals):
   - Assigned to only 1 project with low point commitment
   - Few recent CRs authored
   - Low meeting load with no blockers noted
   - Note: This may indicate they are ramping, blocked, or doing unlisted work
5. Cross-reference with quarterly roadmap priorities to identify:
   - High-priority projects with insufficient allocation
   - Low-priority work consuming disproportionate resources
6. Generate rebalancing recommendations that account for:
   - Engineer expertise and growth goals
   - Context-switching costs
   - Upcoming PTO or oncall rotations

## Output Format
```
## Team Resource Allocation Report
**Date:** [Date]
**Sprint:** [Current Sprint]

### Allocation Heatmap
| Engineer | Project A | Project B | Project C | Oncall | Meeting Load | Total Load |
|----------|-----------|-----------|-----------|--------|--------------|------------|
| [Name]   | [pts]     | [pts]     | [pts]     | [Y/N]  | [X hrs/wk]   | [Rating]   |

Load Rating: Light / Balanced / Heavy / Overloaded

### Over-Committed Engineers
| Engineer | Active Projects | Sprint Points | Open CRs | Meeting % | Concern |
|----------|----------------|---------------|----------|-----------|---------|

### Under-Utilized Engineers
| Engineer | Active Projects | Sprint Points | Possible Reason |
|----------|----------------|---------------|-----------------|

### Project Staffing vs Priority
| Project/Initiative | Priority | Engineers Assigned | Recommended | Gap |
|-------------------|----------|-------------------|-------------|-----|

### Rebalancing Recommendations
1. [Specific recommendation with rationale]
2. [Specific recommendation with rationale]

### Upcoming Changes
- [PTO, oncall rotations, or other changes that will affect allocation next sprint]
```

## Delivery
Send the full report as a Slack DM to me every Thursday (to inform next sprint planning). Flag any engineer at "Overloaded" status immediately when detected.
