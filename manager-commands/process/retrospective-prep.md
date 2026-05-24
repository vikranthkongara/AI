# Sprint Retrospective Preparation

Gather quantitative and qualitative data for the sprint retrospective, providing the team with facts to ground their discussion.

## Data Sources
- Taskei: Sprint backlog, completed vs. planned tasks, carryover items, story points delivered
- CRUX CRs: Code review cycle times, CR sizes, review bottlenecks
- Pipelines: Deployments attempted, successful, rolled back
- Apollo: Deployment issues, service health during sprint
- Oncall system: Incidents during sprint, pages, severity, resolution times
- Slack: Team channel discussions about pain points, frustrations raised, process suggestions
- Calendar: Sprint ceremonies held/missed, meeting time consumed

## Instructions
1. **What We Shipped**:
   - Query Taskei for all tasks completed in sprint {{SPRINT_ID}}
   - Count story points delivered vs. committed
   - List features/capabilities that reached production
   - Check Pipelines for successful deployments during the sprint
2. **What Slipped**:
   - Query Taskei for tasks planned but not completed (carryover)
   - For each carryover item, identify the reason: scope creep, blocked, underestimated, reprioritized
   - Calculate sprint completion rate (delivered/committed)
3. **Operational Health**:
   - Count incidents during the sprint from oncall system
   - Categorize by severity and root cause theme
   - Calculate: total pages, mean time to resolve, customer impact hours
   - Identify any repeat incidents (same root cause as previous sprints)
4. **Process Signals**:
   - Average CR review cycle time (submission to approval)
   - CRs that took >3 days to merge (what went wrong?)
   - Deployment frequency and success rate
   - Any rollbacks and their cause
5. **Team Sentiment** (from Slack):
   - Search team channels for frustration signals, recurring complaints
   - Look for process improvement suggestions team members made informally
   - Identify themes: tooling pain, communication gaps, unclear requirements, etc.
6. **Time Allocation**:
   - Estimate split: feature work vs. ops/toil vs. meetings vs. unplanned work
   - Compare to previous sprint to spot trends

## Output Format
```
## Sprint {{SPRINT_ID}} Retrospective Data Pack
### Sprint Dates: {{START}} - {{END}}

### Delivery Summary
- Story points committed: [X]
- Story points delivered: [Y] ([Z%] completion rate)
- Features shipped to production: [count]
- Tasks carried over: [count]

### What Shipped
| Item | Owner | Impact |
|------|-------|--------|
| ... | ... | ... |

### What Slipped & Why
| Item | Owner | Reason | New ETA |
|------|-------|--------|---------|
| ... | ... | [Blocked/Underestimated/Reprioritized/Scope Creep] | ... |

### Operational Health
- Total incidents: [count]
- Sev2+: [count]
- Total pages: [count]
- Avg resolution time: [X min]
- Repeat incidents: [count] (themes: [...])
- Unplanned operational work hours: [estimate]

### Process Metrics
| Metric | This Sprint | Last Sprint | Trend |
|--------|-------------|-------------|-------|
| Avg CR cycle time | ... | ... | ... |
| Deployment frequency | ... | ... | ... |
| Deployment success rate | ... | ... | ... |
| Rollbacks | ... | ... | ... |

### Team Sentiment Themes (from Slack)
- Pain point 1: [Theme] - raised [X] times
- Pain point 2: [Theme] - raised [X] times
- Suggestion: [What someone proposed]

### Time Allocation Estimate
| Category | % This Sprint | % Last Sprint |
|----------|--------------|---------------|
| Feature work | ... | ... |
| Operational toil | ... | ... |
| Meetings | ... | ... |
| Unplanned work | ... | ... |

### Suggested Discussion Topics for Retro
1. [Data-backed topic worth discussing]
2. [Data-backed topic worth discussing]
3. [Data-backed topic worth discussing]
```

## Delivery
Send as a Slack DM to me 1 day before the scheduled retrospective meeting. Also post a summary version (Delivery Summary + Operational Health only) in the team channel to give everyone pre-read time.
