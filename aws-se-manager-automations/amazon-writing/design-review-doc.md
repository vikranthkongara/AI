# Design Review Document

Generate a design review document covering problem definition, proposed architecture, alternatives, trade-offs, API contracts, and operational considerations.

## Data Sources
- Internal search: existing architecture docs, service dependencies, API documentation, style guides
- CRs: related code, existing patterns in the codebase
- Pipelines/Apollo: current system metrics, capacity, deployment topology
- Oncall: operational pain points that inform design choices
- Taskei: requirements, acceptance criteria, related work items
- Email/Slack: stakeholder requirements, constraints communicated by partner teams

## Instructions
1. **Problem statement (1-2 paragraphs).** What are we solving? Who is the customer? What are the constraints (latency, throughput, cost, timeline)? Be quantitative about requirements.
2. **Non-goals.** Explicitly state what this design does NOT solve. Prevents scope creep during review.
3. **Proposed architecture (2-3 paragraphs).** Describe the system design at the right level of abstraction: components, data flow, key interactions. Include a description of the architecture diagram (components, arrows, data stores).
4. **Alternatives considered (1 paragraph each).** For each alternative: describe the approach, its strengths, and why it was not chosen. Be fair to alternatives -- show you evaluated them honestly.
5. **Trade-offs.** For the chosen design, explicitly state what you are trading away. Every design has trade-offs; pretending otherwise undermines credibility.
6. **API contracts.** Key interfaces: request/response schemas, error codes, pagination, rate limits. Enough detail for a client team to begin integration planning.
7. **Data model.** Key entities, relationships, access patterns. If using a database, justify the choice (relational vs document vs key-value) based on access patterns.
8. **Operational considerations:**
   - Deployment: how will this roll out? Canary strategy?
   - Monitoring: what alarms and dashboards are needed?
   - Scaling: what is the scaling model? Where are the bottlenecks?
   - Failure modes: what happens when each component fails?
   - Rollback: how do we undo a bad deployment?
9. **Security review.** Authentication, authorization, data encryption (at rest and in transit), input validation, threat model for key attack vectors.
10. **Cost estimate.** Infrastructure cost at current scale and projected scale. Cost per request or per customer.

### Amazon Writing Style Rules
- Specificity: "DynamoDB table with partition key=customerId, sort key=timestamp" not "a NoSQL database"
- Data-driven: "Expected throughput of 10,000 RPS based on current traffic of 3,200 RPS growing 25% QoQ"
- No weasel words: "highly available" must become "99.99% availability via multi-AZ deployment with automated failover under 30 seconds"
- Trade-offs are honest: every "pro" has a "con" -- state both
- Operational thinking: design for failure, not just success
- "So what" for every choice: why this database? Why this pattern? What does the customer gain?

## Output Format
```
[Title: Design Review - <Feature/System Name>]
[Author: <name>] [Date: <date>] [Reviewers: <names>]

Problem Statement
[1-2 paragraphs with quantified requirements]

Non-Goals
- [What this design explicitly does not solve]

Proposed Architecture
[2-3 paragraphs with component descriptions]
[Architecture diagram description]

Alternatives Considered
[1 paragraph per alternative with rationale]

Trade-offs
[Table or paragraph: what we gain vs what we give up]

API Contracts
[Key interfaces with schemas]

Data Model
[Entities, relationships, access patterns]

Operational Considerations
[Deployment, monitoring, scaling, failure modes, rollback]

Security
[Auth, encryption, input validation, threat model]

Cost Estimate
[Infrastructure cost at current and projected scale]

Open Questions
[Items requiring decision or further investigation]
```

## Delivery
Save as draft document. Send to specified reviewers via Slack DM or email. If a design review meeting is on the calendar, attach to the invite and request reviewers read in advance.
