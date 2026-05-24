# Architecture Review Preparation

Compile all materials and context needed for an upcoming architecture review, including design documents, open questions, stakeholder list, and discussion points.

## Data Sources
- Taskei (architecture review tasks, design doc links, related epics)
- CRUX CRs (prototype CRs or proof-of-concept code)
- Email/Outlook (design doc review threads, stakeholder feedback)
- Calendar (scheduled review meeting details, attendee list)
- Slack DMs (informal discussions about the design)

## Instructions
1. Check calendar for the next scheduled architecture review meeting. Identify:
   - Meeting title and date/time
   - Current attendee list
   - Any linked documents in the calendar invite
2. Query Taskei for the epic or task associated with this architecture review. Collect:
   - Design document links (wiki pages, quip docs)
   - Related tasks showing scope of the project
   - Requirements or constraints documented in tickets
3. Check email for any threads related to this design:
   - Prior feedback from stakeholders
   - Open questions that were raised but not resolved
   - Approval or concern signals from senior engineers
4. Check CRUX for any prototype or proof-of-concept CRs related to this project:
   - Experimental code that validates the approach
   - Performance benchmarks
   - Compatibility test results
5. Compile a list of open questions and decision points:
   - Technical trade-offs that need group consensus
   - Alternatives that were considered and their pros/cons
   - Areas where more data is needed
6. Identify stakeholders who should attend but are not on the invite:
   - Owners of dependent services
   - Security reviewers (if applicable)
   - Operational owners who will run the service
7. Generate a pre-read summary that attendees can review before the meeting.

## Output Format
```
## Architecture Review Prep
**Project:** [Project Name]
**Review Date:** [Date/Time]
**Facilitator:** [Name]

### Attendees
| Name | Role | Confirmed | Notes |
|------|------|-----------|-------|
[Current attendee list]

### Suggested Additional Attendees
| Name | Reason |
|------|--------|

### Design Documents
| Document | Author | Last Updated | Status |
|----------|--------|--------------|--------|
[Links to all relevant docs]

### Project Context
- **Problem Statement:** [Brief summary]
- **Scope:** [What's in/out of scope]
- **Timeline:** [Target delivery date]
- **Related Epics:** [Taskei links]

### Prototype/POC Evidence
| CR | Description | Key Finding |
|----|-------------|-------------|

### Open Questions for Discussion
1. [Question] - Context: [Why this matters]
2. [Question] - Context: [Why this matters]
3. [Question] - Context: [Why this matters]

### Decision Points
| Decision | Option A | Option B | Recommendation | Trade-offs |
|----------|----------|----------|----------------|------------|

### Prior Feedback Summary
| Stakeholder | Feedback | Status |
|-------------|----------|--------|

### Pre-Read Summary (send to attendees)
[2-3 paragraph summary of the design, key decisions to be made, and what attendees should prepare]

### Suggested Agenda
1. [Topic] - [X min] - [Presenter]
2. [Topic] - [X min] - [Presenter]
3. Open Discussion - [X min]
4. Decisions & Next Steps - [X min]
```

## Delivery
Send the prep document as a Slack DM to me 48 hours before the scheduled review. Also prepare a shorter pre-read summary suitable for sending to all attendees via email 24 hours before the meeting.
