# Individual Development Plan Update

Review and update an engineer's individual development plan, tracking learning progress and identifying upcoming growth opportunities.

## Data Sources
- Taskei: Development-related tasks, learning goals, stretch assignments in progress
- CRUX CRs: Evidence of new skill application (new languages, patterns, architectures)
- Calendar: Training sessions attended, mentoring meetings, tech talks, reading groups
- Slack: Learning-related discussions, knowledge sharing, questions in new domains
- Pipelines: New types of deployments or services they've taken on
- Email (Outlook): Training enrollments, conference registrations, certifications

## Instructions
1. Retrieve {{ENGINEER_NAME}}'s current Individual Development Plan (IDP) from Taskei or last documented version. This should include:
   - Target skills to develop
   - Learning activities planned
   - Stretch assignments identified
   - Timeline and milestones
2. For each planned learning activity, check for evidence of completion:
   - Calendar: Did they attend scheduled training, reading groups, tech talks?
   - CRs: Are they applying new skills in their code? (new frameworks, languages, patterns)
   - Slack: Are they discussing new topics, sharing learnings, asking questions in new domains?
3. For each stretch assignment:
   - Check Taskei for progress on the assignment
   - Check CRs for related code contributions
   - Assess whether the assignment is providing the intended growth
4. Identify new opportunities that have emerged since the plan was last updated:
   - New projects on the team roadmap that align with their growth areas
   - Upcoming oncall rotations for services they want to learn
   - Cross-team collaborations that would expand their scope
   - Tech talks they could give to solidify learning
5. Check if any development plan items are stalled and diagnose why:
   - Competing priorities crowding out learning time
   - Missing prerequisites or enablers
   - Changed interests or career direction
6. Draft updated plan recommendations.

## Output Format
```
## Development Plan Update: {{ENGINEER_NAME}}
### Plan Period: {{START_DATE}} - {{END_DATE}}
### Last Reviewed: {{LAST_REVIEW_DATE}}

### Skill Development Progress
| Skill Area | Target | Current Evidence | Status |
|------------|--------|-----------------|--------|
| [e.g., System Design] | [Target proficiency] | [What they've done] | [On Track/Stalled/Complete] |
| [e.g., New Language] | [Target proficiency] | [What they've done] | [On Track/Stalled/Complete] |

### Learning Activities
| Activity | Planned Date | Status | Notes |
|----------|-------------|--------|-------|
| [Training/course] | ... | Done/Scheduled/Missed | ... |
| [Tech talk attendance] | ... | Done/Scheduled/Missed | ... |
| [Reading/self-study] | ... | Done/In Progress/Not Started | ... |

### Stretch Assignments
| Assignment | Growth Area | Progress | Learning Observed |
|-----------|-------------|----------|-------------------|
| [Project/task] | [Skill it develops] | [% complete] | [What they've gained] |

### Stalled Items & Root Causes
- [Item]: Stalled because [reason]. Suggested fix: [action]

### New Opportunities Identified
1. **[Opportunity]**: Available [when]. Develops [skill]. Action needed: [what to discuss]
2. **[Opportunity]**: Available [when]. Develops [skill]. Action needed: [what to discuss]

### Recommended Plan Updates
- Add: [New activity/goal based on emerging opportunities]
- Modify: [Existing item that needs timeline/scope adjustment]
- Remove: [Item no longer relevant and why]

### 1:1 Discussion Guide
- Ask about: [Their interest level in new opportunities]
- Offer: [Support or resources I can provide]
- Align on: [Updated priorities for development time]
```

## Delivery
Send as a Slack DM to me one week before our scheduled IDP review (check calendar for the meeting). If no specific IDP review is scheduled, send monthly on the first Monday.
