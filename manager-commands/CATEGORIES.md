# Categories - Detailed Breakdown

This document provides a detailed breakdown of every prompt category with one-line descriptions for each prompt. Designed for quick scanning and AI tool ingestion.

---

## 1. Daily Reports (10 prompts)

| # | Prompt | Description |
|---|--------|-------------|
| 1 | morning-ops-briefing | Aggregates overnight deployments, alarms, and blockers into a single morning summary |
| 2 | deployment-status | Reports on all deployments across environments in the last 24 hours |
| 3 | cr-queue-depth | Shows code reviews awaiting action, sorted by age and priority |
| 4 | blocker-escalation | Identifies tasks blocked for more than 48 hours and drafts escalation messages |
| 5 | oncall-handoff-summary | Summarizes overnight oncall activity for clean morning handoff |
| 6 | sprint-burndown-snapshot | Current sprint progress with trajectory projection |
| 7 | team-availability | Shows who is OOO, oncall, or in back-to-back meetings today |
| 8 | pr-merge-velocity | Tracks how quickly PRs are being reviewed and merged today |
| 9 | build-health | Reports on broken builds, flaky tests, and pipeline failures |
| 10 | end-of-day-wrap | Summarizes what was accomplished today and flags carry-over items |

---

## 2. KPI Metrics (10 prompts)

| # | Prompt | Description |
|---|--------|-------------|
| 1 | dora-deployment-frequency | Calculates deployment frequency over rolling 7/30/90 day windows |
| 2 | dora-lead-time | Measures lead time from commit to production deployment |
| 3 | dora-change-failure-rate | Tracks percentage of deployments causing incidents or rollbacks |
| 4 | dora-mttr | Calculates mean time to recovery from production incidents |
| 5 | cycle-time-breakdown | Breaks down cycle time into coding, review, testing, and deploy phases |
| 6 | sprint-velocity-trend | Shows velocity trends over rolling 6 sprints with confidence intervals |
| 7 | service-availability | Reports service uptime against SLA targets with error budget remaining |
| 8 | pr-review-latency | Percentile distribution of time from PR open to first review |
| 9 | defect-escape-rate | Tracks bugs found in production vs. caught in testing/review |
| 10 | engineering-efficiency-ratio | Ratio of feature work to maintenance, toil, and interrupt-driven work |

---

## 3. Engineer Performance (10 prompts)

| # | Prompt | Description |
|---|--------|-------------|
| 1 | individual-output-summary | Code commits, PRs, and CRs per engineer over configurable window |
| 2 | review-quality-score | Assesses thoroughness and value of code review comments given |
| 3 | mentorship-signals | Detects pairing sessions, review teaching moments, and knowledge sharing |
| 4 | growth-trajectory | Tracks increasing scope, complexity, and independence over time |
| 5 | collaboration-index | Measures cross-team contributions, helping behaviors, and unblocking others |
| 6 | tech-debt-contributor | Identifies who is adding vs. reducing technical debt |
| 7 | burnout-risk-flags | Detects late-night commits, weekend work, and declining output patterns |
| 8 | oncall-load-fairness | Ensures oncall burden is distributed equitably across the team |
| 9 | skill-development-tracker | Maps skill growth against career level expectations |
| 10 | promotion-readiness-signal | Aggregates signals indicating readiness for next level |

---

## 4. Team Operations (10 prompts)

| # | Prompt | Description |
|---|--------|-------------|
| 1 | external-dependency-risk | Identifies dependencies on other teams with risk of delay |
| 2 | capacity-vs-demand | Compares team capacity against incoming work requests |
| 3 | tech-debt-accumulation | Tracks technical debt growth rate and highest-interest items |
| 4 | security-compliance-posture | Reports on open security findings, patching status, and compliance gaps |
| 5 | tooling-friction-report | Identifies developer experience pain points from build times, tool failures |
| 6 | bus-factor-analysis | Detects single points of failure in code ownership and knowledge |
| 7 | on-call-health | Tracks alarm volume trends, false positive rates, and response times |
| 8 | infrastructure-cost-trend | Monitors cloud spend trends and identifies optimization opportunities |
| 9 | cross-team-contract-health | Status of API contracts and integration points with other teams |
| 10 | operational-readiness | Assesses team readiness for upcoming launches or migrations |

---

## 5. Communication (10 prompts)

| # | Prompt | Description |
|---|--------|-------------|
| 1 | weekly-status-email | Pre-drafts weekly status update for leadership chain |
| 2 | stakeholder-project-update | Generates project-specific updates for non-technical stakeholders |
| 3 | postmortem-summary | Summarizes incident postmortems with key findings and action items |
| 4 | cross-team-coordination | Drafts coordination messages for multi-team initiatives |
| 5 | escalation-draft | Prepares escalation messages with context, impact, and ask |
| 6 | sprint-review-narrative | Converts sprint data into a narrative for review meetings |
| 7 | quarterly-team-update | Broader team accomplishments and direction for quarterly sharing |
| 8 | new-hire-introduction | Drafts team introduction messages for new team members |
| 9 | knowledge-share-announcement | Promotes internal tech talks, design reviews, and documentation |
| 10 | risk-communication | Articulates technical risks in business-understandable language |

---

## 6. Planning (10 prompts)

| # | Prompt | Description |
|---|--------|-------------|
| 1 | sprint-planning-data-pack | Assembles velocity, capacity, and backlog data for sprint planning |
| 2 | okr-progress-snapshot | Current progress against quarterly OKRs with trajectory |
| 3 | roadmap-dependency-map | Visualizes dependencies between roadmap items and external teams |
| 4 | launch-readiness-checklist | Comprehensive pre-launch checklist covering ops, testing, docs |
| 5 | resource-planning-scenario | Models different staffing scenarios against delivery commitments |
| 6 | quarterly-goal-proposal | Drafts next quarter goals based on current trajectory and priorities |
| 7 | backlog-grooming-prep | Prioritizes and annotates backlog items for grooming sessions |
| 8 | migration-planning | Assesses scope, risk, and timeline for system migrations |
| 9 | capacity-forecast | Projects team capacity over next 4-8 weeks including PTO |
| 10 | tech-investment-proposal | Builds the case for technical investment with ROI framing |

---

## 7. Incidents (10 prompts)

| # | Prompt | Description |
|---|--------|-------------|
| 1 | active-incident-status | Real-time summary of any active incidents and ownership |
| 2 | incident-trend-30d | Analyzes incident patterns over the last 30 days |
| 3 | incident-trend-90d | Longer-term incident trend analysis with seasonal patterns |
| 4 | sla-compliance-report | Tracks SLA adherence and highlights at-risk commitments |
| 5 | alarm-fatigue-detection | Identifies noisy alarms that should be tuned or suppressed |
| 6 | root-cause-patterns | Clusters incidents by root cause to identify systemic issues |
| 7 | mttr-by-severity | Breaks down mean time to resolve by incident severity level |
| 8 | incident-response-quality | Assesses quality of incident response process execution |
| 9 | near-miss-tracker | Identifies near-misses that could have become incidents |
| 10 | incident-action-item-aging | Tracks completion rate of post-incident action items |

---

## 8. Hiring (5 prompts)

| # | Prompt | Description |
|---|--------|-------------|
| 1 | pipeline-health | Current state of recruiting pipeline with conversion rates per stage |
| 2 | interview-loop-status | Upcoming interviews, feedback pending, and scheduling gaps |
| 3 | onboarding-progress | New hire onboarding milestone tracking and blockers |
| 4 | time-to-productivity | Measures ramp-up time for recent hires against benchmarks |
| 5 | offer-acceptance-trends | Tracks offer acceptance rates and identifies drop-off reasons |

---

## 9. 1:1 Meetings (10 prompts)

| # | Prompt | Description |
|---|--------|-------------|
| 1 | one-on-one-prep | Assembles context for upcoming 1:1 including recent work and signals |
| 2 | career-growth-discussion | Prepares talking points for career development conversations |
| 3 | workload-balance-check | Assesses whether engineer workload is sustainable and balanced |
| 4 | recognition-opportunities | Identifies recent wins worth calling out and celebrating |
| 5 | feedback-preparation | Drafts constructive feedback with specific examples |
| 6 | goal-progress-review | Reviews progress on individually-set goals and milestones |
| 7 | skip-level-prep | Prepares context for skip-level conversations with reports' reports |
| 8 | return-from-leave-briefing | Catches up an engineer returning from extended leave |
| 9 | performance-concern-framing | Structures a difficult conversation about performance gaps |
| 10 | follow-up-tracker | Ensures commitments from previous 1:1s are being tracked |

---

## 10. Process (15 prompts)

| # | Prompt | Description |
|---|--------|-------------|
| 1 | retrospective-insights | Aggregates themes from recent retrospectives for action |
| 2 | meeting-time-audit | Calculates team meeting load and identifies optimization opportunities |
| 3 | knowledge-silo-detection | Identifies code areas with single-person ownership risk |
| 4 | automation-opportunity-scan | Finds repetitive manual processes ripe for automation |
| 5 | process-compliance-check | Verifies adherence to team agreements and best practices |
| 6 | toil-measurement | Quantifies time spent on repetitive operational work |
| 7 | documentation-freshness | Identifies stale documentation that needs updating |
| 8 | decision-log-maintenance | Ensures architectural decisions are properly recorded |
| 9 | experiment-tracker | Tracks active experiments, A/B tests, and their outcomes |
| 10 | feedback-loop-health | Measures speed and quality of feedback loops in the dev process |
| 11 | handoff-quality | Assesses quality of information transfer between team members |
| 12 | workflow-bottleneck-finder | Identifies where work gets stuck in the development pipeline |
| 13 | team-agreement-review | Surfaces team agreements due for periodic review |
| 14 | ceremony-effectiveness | Evaluates whether agile ceremonies are providing value |
| 15 | continuous-improvement-backlog | Maintains and prioritizes process improvement ideas |

---

## 11. Amazon Writing (15 prompts)

| # | Prompt | Description |
|---|--------|-------------|
| 1 | qbr-narrative | Drafts Quarterly Business Review narrative with metrics and insights |
| 2 | wbr-data-pack | Assembles Weekly Business Review data with commentary on anomalies |
| 3 | ybr-strategic-summary | Drafts Yearly Business Review strategic section |
| 4 | pr-faq-new-initiative | Structures a PR/FAQ document for a proposed new initiative |
| 5 | six-pager-proposal | Outlines a 6-pager long-form proposal with tenets and alternatives |
| 6 | coe-write-up | Drafts Correction of Error document with timeline and action items |
| 7 | op1-planning-input | Prepares OP1 annual planning input with resource asks |
| 8 | op2-planning-input | Prepares OP2 mid-year planning adjustments |
| 9 | mechanisms-proposal | Proposes new mechanisms to address recurring problems |
| 10 | working-backwards-draft | Structures a working-backwards document from customer need |
| 11 | two-pager-brief | Concise 2-page briefing document for leadership review |
| 12 | goal-cascade-document | Documents how team goals connect to org and company goals |
| 13 | bar-raiser-debrief | Summarizes interview debrief using structured evaluation format |
| 14 | invention-disclosure | Structures an invention disclosure for patent consideration |
| 15 | narrative-appendix-data | Prepares data appendix supporting a narrative document |

---

## 12. Customer Experience (10 prompts)

| # | Prompt | Description |
|---|--------|-------------|
| 1 | cx-metrics-dashboard | Aggregates customer satisfaction metrics across touchpoints |
| 2 | voice-of-customer | Synthesizes customer feedback signals from support, surveys, forums |
| 3 | journey-map-friction | Identifies friction points in customer journey from behavioral data |
| 4 | feature-adoption-rate | Tracks adoption curves for recently launched features |
| 5 | support-ticket-trends | Analyzes support ticket volume, categories, and resolution patterns |
| 6 | error-rate-by-customer-flow | Maps error rates to specific customer-facing workflows |
| 7 | latency-impact-assessment | Correlates latency percentiles with customer experience metrics |
| 8 | accessibility-compliance | Reports on accessibility standards adherence and gaps |
| 9 | customer-segment-health | Breaks down experience quality metrics by customer segment |
| 10 | competitive-experience-gap | Identifies areas where customer experience lags industry benchmarks |
