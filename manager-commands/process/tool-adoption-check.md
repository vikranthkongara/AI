# Tool & Practice Adoption Check

Check team adoption of recommended tools, frameworks, and engineering practices to ensure we're using modern, supported, and secure tooling.

## Data Sources
- CRUX CRs: Build configurations, dependency versions, tool usage in code
- Pipelines: Pipeline configurations, build tool versions, deployment tooling
- Apollo: Deployment configurations, monitoring tool usage
- Taskei: Tech debt tasks related to tool upgrades, migration tracking
- Slack: Discussions about tool issues, requests for help with tools
- Oncall system: Incidents caused by outdated tooling

## Instructions
1. **Build System Currency**:
   - Check Brazil build configurations for the team's packages:
     - Are they using the latest recommended Brazil build system version?
     - Are dependencies up to date or significantly behind?
     - Are deprecated build tools still in use?
   - Check Pipelines configurations:
     - Are pipeline definitions using current best practices?
     - Are there deprecated pipeline stages or actions?
2. **Security Tooling**:
   - Are security scanners enabled and running in the build pipeline?
   - Are static analysis tools configured and not ignored?
   - Are dependency vulnerability scanners active?
   - Are secrets scanning tools in place?
   - Check for any suppressed or ignored security findings
3. **Observability & Monitoring**:
   - Are services using current monitoring frameworks?
   - Are dashboards maintained and current?
   - Are alarms following best practices (not too noisy, not missing coverage)?
   - Are distributed tracing and logging at recommended levels?
4. **Development Practices**:
   - Are code formatting/linting tools configured and enforced?
   - Are pre-commit hooks in place?
   - Is CI/CD fully automated or are there manual gates that shouldn't be?
   - Are feature flags used appropriately for rollouts?
5. **Recommended Tool Adoption**:
   - Cross-reference team's tooling against org-wide recommendations
   - Identify tools recommended by the org that the team hasn't adopted
   - Check for tools the team uses that have been deprecated or replaced
6. **Migration Status**:
   - Check Taskei for any in-progress tool migration tasks
   - Identify migrations that are stalled or behind schedule
   - Note upcoming deprecation deadlines that need attention

## Output Format
```
## Tool & Practice Adoption Report
### Team: {{TEAM_NAME}}
### Assessment Date: {{DATE}}

### Adoption Scorecard
| Category | Status | Currency | Risk |
|----------|--------|----------|------|
| Build system | [Current/Behind/Critical] | [Version info] | [Low/Med/High] |
| Security scanning | [Enabled/Partial/Missing] | ... | ... |
| Monitoring | [Modern/Adequate/Outdated] | ... | ... |
| CI/CD | [Fully automated/Partial/Manual steps] | ... | ... |
| Code quality tools | [Enforced/Configured/Missing] | ... | ... |

### Up to Date (No Action Needed)
- [Tool/Practice]: Current version [X], team uses [X]
- [Tool/Practice]: Properly configured and active

### Behind but Not Critical
| Tool/Practice | Current Version | Team Version | Gap | Migration Effort |
|--------------|----------------|-------------|-----|-----------------|
| ... | ... | ... | [versions behind] | [S/M/L] |

### Critical Gaps (Action Required)
#### [Tool/Practice]
- **Current state**: [What team is using]
- **Recommended state**: [What they should be using]
- **Risk of inaction**: [Security vulnerability / build breakage / support loss]
- **Deadline**: [If deprecation has a date]
- **Migration effort**: [Estimate]
- **Suggested owner**: [Team member who'd be good fit]

### Deprecated Tools Still in Use
| Tool | Deprecated Since | Replacement | Migration Status |
|------|-----------------|-------------|-----------------|
| ... | ... | ... | [Not started/In progress/Blocked] |

### Upcoming Deprecations (Next 6 Months)
| Tool | Deprecation Date | Replacement | Team Action Needed |
|------|-----------------|-------------|-------------------|
| ... | ... | ... | ... |

### Recommendations
1. [Priority 1 action - most urgent/impactful]
2. [Priority 2 action]
3. [Priority 3 action]

### Suggested Sprint Allocation
- Recommend [X] story points per sprint for tool currency maintenance
```

## Delivery
Send as a Slack DM to me quarterly (first week of quarter) or immediately if a critical security tool gap is discovered.
