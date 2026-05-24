# Team Charter Document

Generate a team charter defining mission, vision, tenets, scope, customers, success metrics, and operating rhythm.

## Data Sources
- Internal search: org mission statement, VP-level strategy docs, related team charters
- Taskei: current team backlog, owned services/systems
- Pipelines/Apollo: services owned, operational responsibilities
- Oncall: on-call rotation scope, services paged for
- Email/Slack: team formation context, leadership expectations, cross-team boundary discussions
- Calendar: current meeting cadence, rituals

## Instructions
1. **Mission (1-2 sentences).** What does this team exist to do? Written in terms of customer outcomes, not internal activities. Should be stable over 2-3 years.
2. **Vision (1 paragraph).** What does the world look like in 3 years if this team succeeds? Paint a specific picture of the customer experience.
3. **Tenets (5-7 tenets).** Decision-making principles that resolve real tensions the team faces. Each tenet should have an "especially when" clause. These are not values -- they are practical guidance for daily trade-offs.
4. **Scope: What we own.** Specific systems, services, APIs, experiences, metrics. Be precise: name the repos, the services, the dashboards.
5. **Scope: What we do NOT own.** Explicitly state adjacent areas that are NOT this team's responsibility. Prevents confusion and scope creep.
6. **Customers.** Who does this team serve? Internal teams, external customers, or both? Name them. Describe their needs.
7. **Success metrics.** 3-5 metrics that indicate whether the team is fulfilling its mission. Include current baseline and target.
8. **Operating rhythm.** Weekly cadence: standups, sprint ceremonies, WBR, design reviews, 1:1s. Monthly/quarterly: QBR, planning, retrospectives.
9. **Communication norms.** Where decisions are made (meeting vs doc vs Slack), response time expectations, escalation path, how to request work from this team.
10. **Dependencies.** Teams we depend on, teams that depend on us. Nature of the dependency.

### Amazon Writing Style Rules
- Customer-obsessed: mission and vision written from customer perspective
- Specific: "We own the checkout latency from cart-click to order-confirmation" not "We own checkout"
- No weasel words: "We strive for excellence" is not a tenet. "We ship weekly, even when features are incomplete, because customer feedback on partial solutions is more valuable than internal speculation" is.
- Tenets resolve tensions: if everyone would agree with your tenet, it is not a tenet
- Data-driven: success metrics have numbers, not aspirations
- Actionable: communication norms are concrete enough to follow on day one

## Output Format
```
[Title: Team Charter - <Team Name>]
[Last Updated: <date>]

Mission
[1-2 sentences: why this team exists, in customer terms]

Vision
[1 paragraph: 3-year future state]

Tenets
1. [Tenet] -- especially when [tension it resolves]
2. ...

What We Own
- [System/service 1: brief description]
- [System/service 2: brief description]
- ...

What We Do NOT Own
- [Adjacent area 1: who owns it]
- [Adjacent area 2: who owns it]

Customers
- [Customer 1: needs]
- [Customer 2: needs]

Success Metrics
| Metric | Current | Target | Measurement |
|--------|---------|--------|-------------|
| ...    | ...     | ...    | ...         |

Operating Rhythm
| Cadence | Activity | Day/Time | Participants |
|---------|----------|----------|--------------|
| Weekly  | ...      | ...      | ...          |
| Monthly | ...      | ...      | ...          |

Communication Norms
[How decisions are made, response expectations, escalation path]

Dependencies
| Team | We Need From Them | They Need From Us |
|------|-------------------|-------------------|
| ...  | ...               | ...               |
```

## Delivery
Save as permanent document. Share via Slack in team channel. Send to new team members on their first day. Review and update quarterly.
