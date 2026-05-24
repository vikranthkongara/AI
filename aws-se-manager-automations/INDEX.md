# Prompt Index

A flat index of all 125 prompt files with full paths and one-line descriptions. Designed for AI tool ingestion and rapid project summarization.

---

## Daily Reports

```
prompts/daily/morning-ops-briefing.md          - Aggregates overnight deployments, alarms, and blockers into a single morning summary
prompts/daily/deployment-status.md             - Reports on all deployments across environments in the last 24 hours
prompts/daily/cr-queue-depth.md                - Shows code reviews awaiting action, sorted by age and priority
prompts/daily/blocker-escalation.md            - Identifies tasks blocked for more than 48 hours and drafts escalation messages
prompts/daily/oncall-handoff-summary.md        - Summarizes overnight oncall activity for clean morning handoff
prompts/daily/sprint-burndown-snapshot.md      - Current sprint progress with trajectory projection
prompts/daily/team-availability.md             - Shows who is OOO, oncall, or in back-to-back meetings today
prompts/daily/pr-merge-velocity.md             - Tracks how quickly PRs are being reviewed and merged today
prompts/daily/build-health.md                  - Reports on broken builds, flaky tests, and pipeline failures
prompts/daily/end-of-day-wrap.md               - Summarizes what was accomplished today and flags carry-over items
```

## KPI Metrics

```
prompts/kpi/dora-deployment-frequency.md       - Calculates deployment frequency over rolling 7/30/90 day windows
prompts/kpi/dora-lead-time.md                  - Measures lead time from commit to production deployment
prompts/kpi/dora-change-failure-rate.md        - Tracks percentage of deployments causing incidents or rollbacks
prompts/kpi/dora-mttr.md                       - Calculates mean time to recovery from production incidents
prompts/kpi/cycle-time-breakdown.md            - Breaks down cycle time into coding, review, testing, and deploy phases
prompts/kpi/sprint-velocity-trend.md           - Shows velocity trends over rolling 6 sprints with confidence intervals
prompts/kpi/service-availability.md            - Reports service uptime against SLA targets with error budget remaining
prompts/kpi/pr-review-latency.md               - Percentile distribution of time from PR open to first review
prompts/kpi/defect-escape-rate.md              - Tracks bugs found in production vs. caught in testing/review
prompts/kpi/engineering-efficiency-ratio.md    - Ratio of feature work to maintenance, toil, and interrupt-driven work
```

## Engineer Performance

```
prompts/performance/individual-output-summary.md   - Code commits, PRs, and CRs per engineer over configurable window
prompts/performance/review-quality-score.md        - Assesses thoroughness and value of code review comments given
prompts/performance/mentorship-signals.md          - Detects pairing sessions, review teaching moments, and knowledge sharing
prompts/performance/growth-trajectory.md           - Tracks increasing scope, complexity, and independence over time
prompts/performance/collaboration-index.md         - Measures cross-team contributions, helping behaviors, and unblocking others
prompts/performance/tech-debt-contributor.md       - Identifies who is adding vs. reducing technical debt
prompts/performance/burnout-risk-flags.md          - Detects late-night commits, weekend work, and declining output patterns
prompts/performance/oncall-load-fairness.md        - Ensures oncall burden is distributed equitably across the team
prompts/performance/skill-development-tracker.md   - Maps skill growth against career level expectations
prompts/performance/promotion-readiness-signal.md  - Aggregates signals indicating readiness for next level
```

## Team Operations

```
prompts/operations/external-dependency-risk.md     - Identifies dependencies on other teams with risk of delay
prompts/operations/capacity-vs-demand.md           - Compares team capacity against incoming work requests
prompts/operations/tech-debt-accumulation.md       - Tracks technical debt growth rate and highest-interest items
prompts/operations/security-compliance-posture.md  - Reports on open security findings, patching status, and compliance gaps
prompts/operations/tooling-friction-report.md      - Identifies developer experience pain points from build times, tool failures
prompts/operations/bus-factor-analysis.md          - Detects single points of failure in code ownership and knowledge
prompts/operations/on-call-health.md               - Tracks alarm volume trends, false positive rates, and response times
prompts/operations/infrastructure-cost-trend.md    - Monitors cloud spend trends and identifies optimization opportunities
prompts/operations/cross-team-contract-health.md   - Status of API contracts and integration points with other teams
prompts/operations/operational-readiness.md        - Assesses team readiness for upcoming launches or migrations
```

## Communication

```
prompts/communication/weekly-status-email.md           - Pre-drafts weekly status update for leadership chain
prompts/communication/stakeholder-project-update.md    - Generates project-specific updates for non-technical stakeholders
prompts/communication/postmortem-summary.md            - Summarizes incident postmortems with key findings and action items
prompts/communication/cross-team-coordination.md       - Drafts coordination messages for multi-team initiatives
prompts/communication/escalation-draft.md              - Prepares escalation messages with context, impact, and ask
prompts/communication/sprint-review-narrative.md       - Converts sprint data into a narrative for review meetings
prompts/communication/quarterly-team-update.md         - Broader team accomplishments and direction for quarterly sharing
prompts/communication/new-hire-introduction.md         - Drafts team introduction messages for new team members
prompts/communication/knowledge-share-announcement.md  - Promotes internal tech talks, design reviews, and documentation
prompts/communication/risk-communication.md            - Articulates technical risks in business-understandable language
```

## Planning

```
prompts/planning/sprint-planning-data-pack.md      - Assembles velocity, capacity, and backlog data for sprint planning
prompts/planning/okr-progress-snapshot.md          - Current progress against quarterly OKRs with trajectory
prompts/planning/roadmap-dependency-map.md         - Visualizes dependencies between roadmap items and external teams
prompts/planning/launch-readiness-checklist.md     - Comprehensive pre-launch checklist covering ops, testing, docs
prompts/planning/resource-planning-scenario.md     - Models different staffing scenarios against delivery commitments
prompts/planning/quarterly-goal-proposal.md        - Drafts next quarter goals based on current trajectory and priorities
prompts/planning/backlog-grooming-prep.md          - Prioritizes and annotates backlog items for grooming sessions
prompts/planning/migration-planning.md             - Assesses scope, risk, and timeline for system migrations
prompts/planning/capacity-forecast.md              - Projects team capacity over next 4-8 weeks including PTO
prompts/planning/tech-investment-proposal.md       - Builds the case for technical investment with ROI framing
```

## Incidents

```
prompts/incidents/active-incident-status.md        - Real-time summary of any active incidents and ownership
prompts/incidents/incident-trend-30d.md            - Analyzes incident patterns over the last 30 days
prompts/incidents/incident-trend-90d.md            - Longer-term incident trend analysis with seasonal patterns
prompts/incidents/sla-compliance-report.md         - Tracks SLA adherence and highlights at-risk commitments
prompts/incidents/alarm-fatigue-detection.md       - Identifies noisy alarms that should be tuned or suppressed
prompts/incidents/root-cause-patterns.md           - Clusters incidents by root cause to identify systemic issues
prompts/incidents/mttr-by-severity.md              - Breaks down mean time to resolve by incident severity level
prompts/incidents/incident-response-quality.md     - Assesses quality of incident response process execution
prompts/incidents/near-miss-tracker.md             - Identifies near-misses that could have become incidents
prompts/incidents/incident-action-item-aging.md    - Tracks completion rate of post-incident action items
```

## Hiring

```
prompts/hiring/pipeline-health.md                  - Current state of recruiting pipeline with conversion rates per stage
prompts/hiring/interview-loop-status.md            - Upcoming interviews, feedback pending, and scheduling gaps
prompts/hiring/onboarding-progress.md              - New hire onboarding milestone tracking and blockers
prompts/hiring/time-to-productivity.md             - Measures ramp-up time for recent hires against benchmarks
prompts/hiring/offer-acceptance-trends.md          - Tracks offer acceptance rates and identifies drop-off reasons
```

## 1:1 Meetings

```
prompts/one-on-ones/one-on-one-prep.md             - Assembles context for upcoming 1:1 including recent work and signals
prompts/one-on-ones/career-growth-discussion.md    - Prepares talking points for career development conversations
prompts/one-on-ones/workload-balance-check.md      - Assesses whether engineer workload is sustainable and balanced
prompts/one-on-ones/recognition-opportunities.md   - Identifies recent wins worth calling out and celebrating
prompts/one-on-ones/feedback-preparation.md        - Drafts constructive feedback with specific examples
prompts/one-on-ones/goal-progress-review.md        - Reviews progress on individually-set goals and milestones
prompts/one-on-ones/skip-level-prep.md             - Prepares context for skip-level conversations with reports' reports
prompts/one-on-ones/return-from-leave-briefing.md  - Catches up an engineer returning from extended leave
prompts/one-on-ones/performance-concern-framing.md - Structures a difficult conversation about performance gaps
prompts/one-on-ones/follow-up-tracker.md           - Ensures commitments from previous 1:1s are being tracked
```

## Process

```
prompts/process/retrospective-insights.md              - Aggregates themes from recent retrospectives for action
prompts/process/meeting-time-audit.md                  - Calculates team meeting load and identifies optimization opportunities
prompts/process/knowledge-silo-detection.md            - Identifies code areas with single-person ownership risk
prompts/process/automation-opportunity-scan.md         - Finds repetitive manual processes ripe for automation
prompts/process/process-compliance-check.md            - Verifies adherence to team agreements and best practices
prompts/process/toil-measurement.md                    - Quantifies time spent on repetitive operational work
prompts/process/documentation-freshness.md             - Identifies stale documentation that needs updating
prompts/process/decision-log-maintenance.md            - Ensures architectural decisions are properly recorded
prompts/process/experiment-tracker.md                  - Tracks active experiments, A/B tests, and their outcomes
prompts/process/feedback-loop-health.md                - Measures speed and quality of feedback loops in the dev process
prompts/process/handoff-quality.md                     - Assesses quality of information transfer between team members
prompts/process/workflow-bottleneck-finder.md           - Identifies where work gets stuck in the development pipeline
prompts/process/team-agreement-review.md               - Surfaces team agreements due for periodic review
prompts/process/ceremony-effectiveness.md              - Evaluates whether agile ceremonies are providing value
prompts/process/continuous-improvement-backlog.md      - Maintains and prioritizes process improvement ideas
```

## Amazon Writing

```
prompts/amazon-writing/qbr-narrative.md                - Drafts Quarterly Business Review narrative with metrics and insights
prompts/amazon-writing/wbr-data-pack.md                - Assembles Weekly Business Review data with commentary on anomalies
prompts/amazon-writing/ybr-strategic-summary.md        - Drafts Yearly Business Review strategic section
prompts/amazon-writing/pr-faq-new-initiative.md        - Structures a PR/FAQ document for a proposed new initiative
prompts/amazon-writing/six-pager-proposal.md           - Outlines a 6-pager long-form proposal with tenets and alternatives
prompts/amazon-writing/coe-write-up.md                 - Drafts Correction of Error document with timeline and action items
prompts/amazon-writing/op1-planning-input.md           - Prepares OP1 annual planning input with resource asks
prompts/amazon-writing/op2-planning-input.md           - Prepares OP2 mid-year planning adjustments
prompts/amazon-writing/mechanisms-proposal.md          - Proposes new mechanisms to address recurring problems
prompts/amazon-writing/working-backwards-draft.md      - Structures a working-backwards document from customer need
prompts/amazon-writing/two-pager-brief.md              - Concise 2-page briefing document for leadership review
prompts/amazon-writing/goal-cascade-document.md        - Documents how team goals connect to org and company goals
prompts/amazon-writing/bar-raiser-debrief.md           - Summarizes interview debrief using structured evaluation format
prompts/amazon-writing/invention-disclosure.md         - Structures an invention disclosure for patent consideration
prompts/amazon-writing/narrative-appendix-data.md      - Prepares data appendix supporting a narrative document
```

## Customer Experience

```
prompts/customer-experience/cx-metrics-dashboard.md        - Aggregates customer satisfaction metrics across touchpoints
prompts/customer-experience/voice-of-customer.md           - Synthesizes customer feedback signals from support, surveys, forums
prompts/customer-experience/journey-map-friction.md        - Identifies friction points in customer journey from behavioral data
prompts/customer-experience/feature-adoption-rate.md       - Tracks adoption curves for recently launched features
prompts/customer-experience/support-ticket-trends.md       - Analyzes support ticket volume, categories, and resolution patterns
prompts/customer-experience/error-rate-by-customer-flow.md - Maps error rates to specific customer-facing workflows
prompts/customer-experience/latency-impact-assessment.md   - Correlates latency percentiles with customer experience metrics
prompts/customer-experience/accessibility-compliance.md    - Reports on accessibility standards adherence and gaps
prompts/customer-experience/customer-segment-health.md     - Breaks down experience quality metrics by customer segment
prompts/customer-experience/competitive-experience-gap.md  - Identifies areas where customer experience lags industry benchmarks
```

---

## Summary Statistics

| Category | Count | Directory |
|----------|-------|-----------|
| Daily Reports | 10 | `prompts/daily/` |
| KPI Metrics | 10 | `prompts/kpi/` |
| Engineer Performance | 10 | `prompts/performance/` |
| Team Operations | 10 | `prompts/operations/` |
| Communication | 10 | `prompts/communication/` |
| Planning | 10 | `prompts/planning/` |
| Incidents | 10 | `prompts/incidents/` |
| Hiring | 5 | `prompts/hiring/` |
| 1:1 Meetings | 10 | `prompts/one-on-ones/` |
| Process | 15 | `prompts/process/` |
| Amazon Writing | 15 | `prompts/amazon-writing/` |
| Customer Experience | 10 | `prompts/customer-experience/` |
| **Total** | **125** | |
