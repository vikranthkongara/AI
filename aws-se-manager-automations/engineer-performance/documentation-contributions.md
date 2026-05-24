# Documentation Contributions Report

Track per-engineer documentation contributions including wiki pages, design documents, runbook updates, and README improvements. Documentation work is often invisible but critical for team scalability and operational excellence.

## Data Sources
- CRUX CRs: changes to README files, docs/ directories, wiki pages, runbooks
- Taskei: documentation-tagged tickets, design doc review tasks
- Slack: messages sharing knowledge, FAQs answered in team channels
- Oncall system: runbook creation and update history
- Internal wikis/Quip: document authorship and edit history

## Instructions

1. Query CRUX CRs for the past 30 days. Identify documentation-related changes:
   - README.md updates in any package
   - Changes to files in docs/, documentation/, or wiki/ directories
   - Runbook additions or updates (look for paths containing "runbook", "playbook", "SOP")
   - Inline code documentation improvements (significant comment additions)
   - API documentation changes (Swagger/OpenAPI specs, Coral model docs)

2. Check Quip/wiki systems for:
   - Design documents authored (new docs created)
   - Design documents reviewed (comments and approvals)
   - Operational runbooks created or substantially updated
   - Team wiki pages created or updated
   - Onboarding documentation improvements

3. Query Taskei for:
   - Tickets with documentation labels/tags completed
   - Design doc tasks (writing or reviewing)
   - Knowledge transfer tasks

4. Review Slack activity (team channels only) for:
   - Detailed technical explanations shared (long-form messages explaining systems)
   - FAQ answers that should be documented
   - Links to documentation shared proactively

5. Calculate per-engineer metrics:
   - Total documentation artifacts produced (docs, runbooks, READMEs)
   - Documentation CRs as percentage of total CRs
   - Design docs authored vs reviewed
   - Runbook freshness (did they update runbooks for services they changed?)
   - Knowledge sharing frequency (Slack explanations, brown bags presented)

6. Assess documentation quality signals:
   - Are runbooks kept in sync with code changes?
   - Do design docs follow team templates?
   - Are READMEs updated when interfaces change?

## Output Format

```
## Documentation Contributions Report
**Period:** Past 30 days
**Team:** [team name]

### Per-Engineer Summary

| Engineer | Docs Authored | Docs Reviewed | Runbook Updates | README Updates | Doc CR Ratio |
|----------|--------------|---------------|-----------------|----------------|--------------|
| [name]   | [n]          | [n]           | [n]             | [n]            | [%]          |

### Notable Contributions
- **[name]:** [e.g., "Authored design doc for new caching layer, updated 3 runbooks after service migration"]
- **[name]:** [e.g., "Created comprehensive onboarding guide, added API examples to 2 packages"]
- **[name]:** [e.g., "Reviewed 5 design docs providing detailed feedback, updated team wiki processes"]

### Documentation Health
- Services with up-to-date runbooks: [n/total] ([%])
- Packages with current READMEs: [n/total] ([%])
- Design docs completed this period: [n]
- Design docs in review: [n]
- Stale documentation identified: [list items needing updates]

### Gaps Identified
- Services missing runbooks: [list]
- Recent code changes without corresponding doc updates: [list CRs]
- Engineers with zero documentation contributions: [list - for coaching conversation]

### Recommendations
1. [e.g., "Schedule doc sprint to address [n] stale runbooks"]
2. [e.g., "Recognize [engineer] for documentation leadership"]
3. [e.g., "Add documentation checklist to CR template"]
```

## Delivery
Send the formatted report as a Slack DM to me. Flag any services that have had code changes in the past 30 days but zero runbook updates - these are operational risks worth discussing in the next team meeting.
