# UX Debt Inventory

Catalog UX debt: known usability issues, accessibility gaps, outdated UI patterns, and customer confusion points derived from support data.

## Data Sources
- Internal search: UI component library, design system documentation, accessibility audit results
- Oncall: customer-reported confusion, repeat support contacts for UI issues
- Taskei: existing UX bug tickets, deferred design improvements
- Email/Slack: customer feedback about UI, designer notes on known issues
- CRs: UI-related code with TODO comments, deprecated component usage

## Instructions
1. **Known usability issues.** Catalog all identified usability problems. For each:
   - Description of the issue (what the customer experiences)
   - Affected workflow(s)
   - Severity: Critical (blocks task completion), Major (causes significant confusion/delay), Minor (cosmetic or slight friction)
   - Evidence: support tickets, usability test results, analytics showing confused behavior
   - Customer impact: how many customers affected, how often
   - Age: how long has this been known
2. **Accessibility gaps.** Identify WCAG compliance issues:
   - Screen reader compatibility problems
   - Keyboard navigation gaps
   - Color contrast failures
   - Missing alt text, ARIA labels
   - Focus management issues
   - Severity and affected customer count
3. **Outdated UI patterns.** Components or interactions that do not follow current design system:
   - What pattern is used vs what the design system recommends
   - Why it matters (inconsistency confuses customers, maintenance burden)
   - Effort to update
4. **Customer confusion points from support data.** Analyze support tickets to find UI elements that generate repeat questions:
   - "How do I...?" questions indicate discoverability problems
   - "I thought it would..." questions indicate expectation mismatches
   - "I accidentally..." questions indicate dangerous defaults or unclear actions
5. **Priority ranking.** Score each item by: customer impact (H/M/L) x frequency (H/M/L) x effort to fix (S/M/L). Recommend top 10 items to address.
6. **Debt trend.** Is UX debt growing or shrinking? Compare to last inventory. What is the rate of accrual vs retirement.

### Amazon Writing Style Rules
- Customer-obsessed: describe each issue from the customer's perspective, not the engineer's
- Data-driven: "127 support tickets in 30 days asking how to find the export button" not "customers can't find export"
- No weasel words: "unintuitive interface" must become "8 of 10 usability test participants clicked the wrong button on first attempt"
- Specificity: name the page, the component, the interaction, the exact customer confusion
- "So what": every debt item must have an impact statement and a proposed resolution
- Honest about accumulation: acknowledge what we are choosing to defer and the cost of that choice

## Output Format
```
UX Debt Inventory - <Product/Service> - <Date>

SUMMARY
[Total items: X | Critical: X | Major: X | Minor: X]
[Trend: Growing/Stable/Shrinking | Net change since last inventory: +/-X]

CRITICAL ISSUES (blocks task completion)
| # | Issue | Workflow | Evidence | Customers Affected | Age | Fix Effort |
|---|-------|----------|----------|-------------------|-----|------------|
| 1 | ...   | ...      | ...      | ...               | ... | ...        |

MAJOR ISSUES (significant confusion/delay)
| # | Issue | Workflow | Evidence | Customers Affected | Age | Fix Effort |
|---|-------|----------|----------|-------------------|-----|------------|
| 1 | ...   | ...      | ...      | ...               | ... | ...        |

ACCESSIBILITY GAPS
| # | Issue | WCAG Criterion | Severity | Affected Component | Fix Effort |
|---|-------|---------------|----------|-------------------|------------|
| 1 | ...   | ...           | ...      | ...               | ...        |

OUTDATED PATTERNS
| # | Current Pattern | Recommended Pattern | Pages Affected | Effort |
|---|----------------|--------------------|--------------  |--------|
| 1 | ...            | ...                | ...            | ...    |

CUSTOMER CONFUSION POINTS (from support data)
| # | Question Theme | Frequency | Root Cause | Proposed Fix |
|---|---------------|-----------|-----------|--------------|
| 1 | ...           | ...       | ...       | ...          |

PRIORITY RECOMMENDATIONS (Top 10)
| Rank | Item | Impact | Frequency | Effort | Score | Recommended Sprint |
|------|------|--------|-----------|--------|-------|-------------------|
| 1    | ...  | ...    | ...       | ...    | ...   | ...               |

DEBT TREND
[Paragraph: accrual rate, retirement rate, net direction, risk if unaddressed]
```

## Delivery
Save as persistent document (update rather than replace). Send Slack DM to engineering manager and UX lead with top 5 recommendations. If sprint planning is upcoming, flag items for backlog grooming.
