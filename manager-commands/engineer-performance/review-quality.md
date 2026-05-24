# Review Quality Assessment

Quality of CR reviews given by each engineer: substantive comments vs rubber stamps, review thoroughness, and contribution to code quality through reviews.

## Data Sources
- **CRUX CRs**: All reviews given by team members - comments, approvals, rejections, time spent
- **Taskei**: Post-merge bugs that could have been caught in review
- **Oncall System**: Incidents caused by issues that reviewers missed

## Instructions

1. **Pull all review activity** per engineer (default: last 30 days):
   - Total CRs reviewed
   - CRs approved
   - CRs where they requested changes
   - Comments left per CR
   - Time from review request to first response
   - Time from review request to final approval/rejection

2. **Classify review comments by type**:
   - **Substantive**: Bug identification, logic errors, missing edge cases, security concerns, performance issues, architectural feedback
   - **Improvement**: Better design suggestions, code organization, naming improvements, pattern recommendations
   - **Style/Nit**: Formatting, naming conventions, whitespace (low value if linter handles)
   - **Questions**: Asking for clarification about intent or approach
   - **Approval only**: Approved with no comments (potential rubber stamp)

3. **Identify rubber-stamping patterns**:
   - CRs approved in under 5 minutes for non-trivial changes (>50 lines)
   - CRs approved with zero comments for complex changes
   - Pattern of always approving without requesting changes
   - Large CRs (200+ lines) approved without comments
   - Approvals for unfamiliar code areas (reviewer has no history with that package)

4. **Assess review thoroughness**:
   - Do they catch actual bugs? (Track if their comments identified real issues)
   - Do they review tests or just implementation?
   - Do they check for edge cases and error handling?
   - Do they verify documentation/comments for complex logic?
   - Do they consider operational concerns (logging, monitoring, rollback)?

5. **Track review impact**:
   - Bugs caught in review that would have been production issues
   - Design improvements suggested that were adopted
   - Post-merge incidents in code they reviewed (missed issues)
   - Authors who improve based on their feedback

6. **Compare to team standards**:
   - Team average comments per review
   - Team average review time
   - Distribution of substantive vs style comments
   - Identify top reviewers as role models

## Output Format

```
# Review Quality Report - [Period: Start Date to End Date]

## Team Summary
- Total CRs reviewed: [count]
- Avg comments per review: [X]
- Avg time to first review: [hours]
- Rubber-stamp rate (approval <5min, no comments): [X]%
- Bugs caught in review: [count]
- Target: <10% rubber-stamp rate, >2 substantive comments/review

## Per-Engineer Review Quality

### [Engineer Name]

| Metric | Value | Team Avg | Assessment |
|--------|-------|----------|-----------|
| CRs reviewed | [count] | [avg] | - |
| Avg comments/review | [X] | [avg] | [Good/Below/Above] |
| Substantive comments | [%] | [%] | [Good/Low] |
| Style/nit comments | [%] | [%] | - |
| Rubber-stamp rate | [%] | [%] | [Acceptable/Concerning] |
| Avg response time | [hrs] | [hrs] | [Fast/Slow/On target] |
| Changes requested rate | [%] | [%] | - |
| Bugs caught | [count] | [avg] | - |

**Review Strengths:**
- [Consistently catches concurrency issues]
- [Provides excellent architectural feedback]
- [Very responsive - always reviews within 4 hours]

**Areas for Improvement:**
- [Tends to rubber-stamp large CRs - spent avg 3 min on 200+ line CRs]
- [Comments are mostly style/nit - needs more substantive feedback]
- [Response time above team average]

---
(repeat for each engineer)

## Comment Type Distribution (Team)

| Engineer | Substantive | Improvement | Style/Nit | Questions | Approval Only |
|----------|-------------|-------------|-----------|-----------|---------------|
| [name] | [%] | [%] | [%] | [%] | [%] |

## Rubber-Stamp Flags

| Reviewer | CR | Author | Lines Changed | Review Time | Comments |
|----------|-----|--------|--------------|-------------|----------|
| [name] | CR-xxx | [author] | [lines] | [min] | 0 |

## Post-Merge Issues (Could Have Been Caught in Review)

| CR | Reviewer | Issue Found Post-Merge | Severity | Preventable? |
|----|----------|----------------------|----------|-------------|
| CR-xxx | [name] | [description] | [sev] | [Yes/Maybe/No] |

## Top Reviewers (Role Models)
1. [Name] - [X] substantive comments/review, caught [Y] bugs, [Z]h avg response
2. [Name] - [strengths]

## Recommendations
- [Engineer A]: Discuss review depth in 1:1 - rubber-stamp rate at X%
- [Engineer B]: Excellent reviewer - consider as review mentor for team
- [Engineer C]: Encourage reviewing outside comfort zone for growth
- [Team]: Set expectation of minimum 1 substantive comment per review
- [Team]: Consider review pairing for complex CRs to model good practices
```

## Delivery
- Send as Slack DM to me every other Friday (bi-weekly)
- Use for 1:1 coaching conversations about review practices
- This is manager-only data - do not share individual rubber-stamp rates publicly
- Include specific CR examples when coaching engineers on review quality
