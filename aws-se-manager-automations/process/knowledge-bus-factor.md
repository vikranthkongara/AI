# Knowledge Silos & Bus Factor Analysis

Identify single points of failure in team knowledge: services, systems, or processes that only one person understands, creating risk if they leave, go on vacation, or are unavailable.

## Data Sources
- CRUX CRs: Who commits to which services/packages, diversity of contributors per codebase
- Taskei: Task assignment patterns, who gets assigned which types of work
- Oncall system: Who handles incidents for which services, escalation patterns
- Pipelines: Who deploys which services, deployment ownership concentration
- Apollo: Service ownership and operational knowledge distribution
- Slack: Who gets questions about what, who is the go-to person for specific topics

## Instructions
1. **Code Ownership Concentration**:
   - For each service/package the team owns, analyze CRUX CRs over the last 90 days:
     - How many unique contributors?
     - What percentage of changes come from the top contributor?
     - Are there services with only 1 contributor in the last quarter?
   - Flag any codebase where one person wrote >70% of recent changes
2. **Operational Knowledge Concentration**:
   - From oncall system, check incident resolution patterns:
     - Which incidents consistently require escalation to one specific person?
     - Are there services where only one person has ever resolved an incident?
   - From Pipelines, check who deploys what:
     - Are there services only one person deploys?
     - Who has the credentials/access/knowledge for each deployment?
3. **Question Routing** (Knowledge Demand):
   - Search Slack for patterns: who gets DM'd or @mentioned for specific topics?
   - Identify people who are the sole answerer for certain domains
   - Look for "ask X about Y" patterns indicating single-threaded knowledge
4. **Process Knowledge**:
   - Identify processes only one person knows how to run
   - Check for tools/scripts maintained by a single person
   - Look for undocumented tribal knowledge
5. **Risk Assessment**:
   - For each identified silo, assess:
     - Impact if that person is unavailable for 2 weeks
     - Ease of knowledge transfer (documented vs. tribal)
     - Current documentation status
6. **Mitigation Recommendations**:
   - Suggest pairing opportunities, documentation sprints, rotation schedules
   - Identify which silos are most urgent to address (highest impact + lowest documentation)

## Output Format
```
## Knowledge Silo & Bus Factor Report
### Team: {{TEAM_NAME}}
### Assessment Date: {{DATE}}

### Bus Factor Summary
| Service/Area | Bus Factor | Primary Expert | Backup | Risk Level |
|-------------|-----------|----------------|--------|------------|
| [Service A] | 1 | [Person] | None | CRITICAL |
| [Service B] | 1 | [Person] | Partial: [Person] | HIGH |
| [Service C] | 2 | [Person] | [Person] | MODERATE |
| [Service D] | 3+ | Multiple | Multiple | LOW |

### Critical Silos (Bus Factor = 1, High Impact)
#### [Service/Area]
- **Single expert**: [Person]
- **Evidence**: [X% of CRs, sole incident responder, only deployer]
- **Impact if unavailable**: [What breaks or stalls]
- **Documentation status**: [None / Partial / Exists but outdated]
- **Mitigation priority**: URGENT

### Knowledge Demand Map (Who Gets Asked What)
| Topic/Service | Go-To Person | Question Volume | Backup Available |
|--------------|-------------|-----------------|-----------------|
| ... | ... | [High/Med/Low] | [Yes/No/Partial] |

### Concentration Metrics
- Services with single contributor (90 days): [count] / [total services]
- Average bus factor across services: [X]
- Team members carrying disproportionate knowledge load: [names]

### Mitigation Plan
#### Immediate Actions (Next 2 Weeks)
1. **Pair [Person A] with [Person B] on [Service]**: [Specific activity - joint deployment, code walkthrough, etc.]
2. **Document [Process/Service]**: Assign [Person] to write runbook, have [other Person] validate by following it

#### Short-Term (This Quarter)
1. **Rotate oncall ownership for [Service]**: Spread operational knowledge
2. **Shadow deployments**: [Person B] shadows [Person A] for next 3 deployments of [Service]
3. **Knowledge transfer sessions**: Schedule [specific topics]

#### Long-Term (Structural Changes)
1. **Code review rotation**: Ensure diverse reviewers for critical services
2. **Mandatory documentation**: For any service with bus factor 1
3. **Cross-training sprints**: Dedicate sprint capacity to knowledge sharing

### Vacation Risk Check
- [Person] has PTO in [timeframe]: Services at risk: [list]
- Recommended pre-vacation handoff: [specific actions]
```

## Delivery
Send as a Slack DM to me monthly on the second Monday. If any team member has upcoming PTO and they are the sole owner of a critical service, send an alert 2 weeks before their PTO starts.
