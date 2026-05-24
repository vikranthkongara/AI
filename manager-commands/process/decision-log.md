# Decision Log Compilation

Compile recent technical and process decisions made by the team, creating an institutional record with context, rationale, and outcomes.

## Data Sources
- Slack: Discussions that resulted in decisions, announcements of changes, "we decided to..." messages
- CRUX CRs: Design decisions embedded in code reviews, architecture choices with rationale in descriptions
- Taskei: Tasks that represent decision outcomes, planning decisions reflected in sprint priorities
- Calendar: Design review meetings, architecture discussions, planning sessions
- Email (Outlook): Decisions communicated via email, cross-team agreements

## Instructions
1. **Identify Decisions Made** (last 2 weeks):
   - Search Slack team channels for decision signals: "we decided," "going with," "let's do," "the plan is," "agreed to," architecture discussions that concluded
   - Check CRUX CRs for design decisions: CRs with design doc links, architectural CRs with extensive discussion, CRs where alternatives were discussed in comments
   - Check Taskei for priority decisions: tasks re-prioritized, scope decisions, trade-off choices
   - Review calendar for design review or architecture meeting outcomes
   - Check email for cross-team agreements or escalation resolutions
2. **For Each Decision, Document**:
   - What was decided
   - When it was decided
   - Who was involved in the decision
   - What alternatives were considered
   - Why this option was chosen (rationale)
   - What constraints or trade-offs influenced the choice
   - Expected outcome or success criteria
   - Reversibility (easy to undo, hard to undo, one-way door)
3. **Categorize Decisions**:
   - Technical architecture
   - Technology/tool choice
   - Process change
   - Priority/roadmap
   - Operational
   - People/team structure
4. **Track Decision Outcomes** (for decisions made >4 weeks ago):
   - Did the decision achieve its intended outcome?
   - Any unintended consequences?
   - Would we make the same decision again?

## Output Format
```
## Decision Log
### Team: {{TEAM_NAME}}
### Period: {{DATE_RANGE}}
### Decisions Recorded: [count]

### Recent Decisions

#### Decision #[N]: [Short Title]
- **Date**: {{DATE}}
- **Category**: [Technical/Process/Priority/Operational]
- **Decision**: [Clear statement of what was decided]
- **Context**: [What problem or situation prompted this decision]
- **Alternatives Considered**:
  - Option A: [Description] - Rejected because [reason]
  - Option B: [Description] - Rejected because [reason]
- **Rationale**: [Why this option was chosen]
- **Trade-offs Accepted**: [What we gave up]
- **Decision Makers**: [Who was involved]
- **Reversibility**: [One-way door / Two-way door / Easily reversible]
- **Success Criteria**: [How we'll know if this was right]
- **Source**: [Link to Slack thread/CR/doc where this was discussed]

[Repeat for each decision...]

### Decision Outcomes (Decisions from 4+ Weeks Ago)
| Decision | Date | Outcome | Assessment |
|----------|------|---------|-----------|
| [Title] | ... | [What happened] | [Good call / Needs revisiting / Regret] |

### Patterns & Observations
- Decision velocity: [Are we making decisions quickly enough?]
- Decision quality: [Are past decisions aging well?]
- Participation: [Are the right people involved in decisions?]
- Documentation: [Are decisions being captured or lost?]

### Decisions Pending (Need Resolution)
| Topic | Blocking | Owner | Target Date |
|-------|----------|-------|-------------|
| ... | [What it blocks] | [Who should decide] | ... |
```

## Delivery
Send as a Slack DM to me every 2 weeks (bi-weekly on Fridays). I will review and share relevant portions with the team to maintain institutional memory.
