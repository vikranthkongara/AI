# Quarterly Planning Input Compilation

Compile comprehensive inputs for next quarter's planning cycle: tech debt inventory, customer requests, headcount needs, dependencies, and capacity estimates.

## Data Sources
- Taskei: Backlog items, tech debt tickets, feature requests, dependency tickets
- CRUX CRs: Patterns indicating systemic issues needing investment
- Pipelines: Infrastructure needs, pipeline improvements needed
- Apollo: Service health trends indicating investment needs
- Oncall system: Incident trends, operational burden by service, repeat incidents
- Slack: Team requests, customer escalations, pain points raised
- Email (Outlook): Stakeholder requests, leadership priorities, partner team asks
- Calendar: Upcoming deadlines, committed milestones, external dependencies

## Instructions
1. **Tech Debt Inventory**:
   - Query Taskei for all tickets tagged as tech debt, sorted by priority
   - From oncall system, identify services with recurring incidents (systemic issues)
   - From CRs, identify areas with frequent workarounds or "TODO" comments
   - Estimate effort and categorize: critical (blocking other work), important (slowing us down), nice-to-have
   - Total story points of tech debt backlog
2. **Customer & Stakeholder Asks**:
   - Check email for feature requests from stakeholders or partner teams
   - Check Taskei for externally-requested items in the backlog
   - Check Slack for customer escalation patterns (what do customers want?)
   - Prioritize by: customer impact, revenue/metric impact, strategic alignment
3. **Headcount & Capacity Analysis**:
   - Current team size and expected changes (departures, transfers, new hires in pipeline)
   - Calculate available capacity for next quarter (accounting for oncall, interviews, PTO)
   - Identify skill gaps that hiring could address
   - Estimate capacity needed vs. demand from backlog + new asks
4. **Dependency Mapping**:
   - Identify cross-team dependencies for planned work
   - Check status of dependencies promised to us by other teams
   - Identify dependencies other teams have on us (commitments we need to honor)
   - Flag any dependency risks or misalignment
5. **Operational Investment Needs**:
   - From oncall trends, identify services needing reliability investment
   - From Pipelines, identify deployment improvements needed
   - Estimate ops burden reduction achievable with investment
6. **Risk Assessment**:
   - What could derail the quarter: known risks, dependency failures, attrition
   - What's the minimum viable plan if capacity is constrained?
7. **Team Input Synthesis**:
   - Compile suggestions from team 1:1s about what to prioritize
   - Note team energy/enthusiasm signals for different project types

## Output Format
```
## Quarterly Planning Inputs
### Team: {{TEAM_NAME}}
### Planning For: Q[X] {{YEAR}}
### Compiled: {{DATE}}

### Executive Summary
- Available capacity: [X] engineer-weeks (after overhead)
- Demand (backlog + asks): [Y] engineer-weeks
- Capacity gap: [Z] engineer-weeks ([deficit/surplus])
- Top recommendation: [1-sentence priority call]

### Capacity Model
| Factor | Value | Notes |
|--------|-------|-------|
| Engineers | [count] | [any changes expected] |
| Weeks in quarter | 13 | |
| Gross capacity | [X] eng-weeks | |
| Oncall overhead | -[X] eng-weeks | [rotations x weeks] |
| Interview load | -[X] eng-weeks | [estimated loops] |
| PTO/holidays | -[X] eng-weeks | [known PTO + holidays] |
| Meetings/ceremonies | -[X] eng-weeks | [% overhead] |
| **Net capacity** | **[X] eng-weeks** | |

### Tech Debt Backlog (Prioritized)
| Priority | Item | Effort | Impact if Addressed | Risk if Ignored |
|----------|------|--------|--------------------|----|
| P1 | ... | [X weeks] | ... | ... |
| P2 | ... | [X weeks] | ... | ... |
| P3 | ... | [X weeks] | ... | ... |
**Total tech debt backlog: [X] engineer-weeks**

### Customer/Stakeholder Requests
| Request | Source | Impact | Effort | Priority Recommendation |
|---------|--------|--------|--------|------------------------|
| ... | [Stakeholder] | [Metric impact] | [X weeks] | [P1/P2/P3] |

### Operational Investment Needs
| Service/Area | Current Pain | Investment Needed | Expected Improvement |
|-------------|-------------|-------------------|---------------------|
| ... | [Incidents/toil] | [X weeks] | [reduced ops by Y%] |

### Dependencies (We Need from Others)
| Dependency | Team | Status | Risk | Mitigation |
|-----------|------|--------|------|-----------|
| ... | [Team] | [Confirmed/At risk/Not started] | [H/M/L] | ... |

### Dependencies (Others Need from Us)
| Commitment | For Team | Effort | Deadline |
|-----------|----------|--------|----------|
| ... | [Team] | [X weeks] | [Date] |

### Headcount Assessment
- Current gaps: [Skills we're missing]
- Attrition risk: [Any concerns]
- Hiring pipeline: [Positions open, candidates in process]
- Recommendation: [Hire for X, backfill Y, or sufficient]

### Risk Register
| Risk | Likelihood | Impact | Mitigation |
|------|-----------|--------|-----------|
| ... | H/M/L | H/M/L | ... |

### Recommended Quarterly Plan (Draft)
| Priority | Theme | Allocation | Key Deliverables |
|----------|-------|-----------|-----------------|
| 1 | [Theme] | [X] eng-weeks ([Y%]) | [What we'll ship] |
| 2 | [Theme] | [X] eng-weeks ([Y%]) | [What we'll ship] |
| 3 | [Theme] | [X] eng-weeks ([Y%]) | [What we'll ship] |
| Buffer | Unplanned | [X] eng-weeks (10%) | [Flexibility] |

### Team Sentiment on Priorities
- Team wants to work on: [themes that energize the team]
- Team is tired of: [areas causing fatigue]
- Consider for morale: [how to balance must-do with want-to-do]
```

## Delivery
Send as a Slack DM to me 2 weeks before quarterly planning begins. Follow up 1 week before with any updates from the intervening period.
