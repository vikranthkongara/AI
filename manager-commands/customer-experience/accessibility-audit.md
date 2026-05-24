# Accessibility Compliance Audit

Perform an accessibility compliance check: WCAG violations, screen reader compatibility, keyboard navigation gaps, color contrast issues, and remediation plan.

## Data Sources
- Internal search: accessibility testing tool results, WCAG compliance reports, design system accessibility docs
- CRs: recent UI changes that may introduce accessibility issues
- Taskei: existing accessibility bugs, remediation items in backlog
- Email/Slack: accessibility team feedback, customer reports of accessibility issues
- Oncall: accessibility-related customer complaints

## Instructions
1. **Scope definition.** Define what is being audited: specific pages, workflows, or components. Note WCAG version and conformance level target (typically WCAG 2.1 AA).
2. **Automated scan results.** Compile results from automated accessibility tools:
   - Total violations by severity (critical, serious, moderate, minor)
   - Violations by WCAG success criterion
   - Violations by component/page
   - Comparison to previous scan (new violations, resolved violations)
3. **Screen reader compatibility.** For key workflows, assess:
   - Are all interactive elements properly labeled?
   - Is the reading order logical?
   - Are state changes announced?
   - Do dynamic content updates notify the user?
   - Test with primary screen readers (NVDA, JAWS, VoiceOver)
4. **Keyboard navigation.** For key workflows:
   - Can all actions be completed without a mouse?
   - Is focus visible at all times?
   - Is focus order logical?
   - Are there keyboard traps?
   - Do custom components handle keyboard events correctly?
5. **Color contrast.** Check all text and interactive elements:
   - Normal text: minimum 4.5:1 contrast ratio
   - Large text: minimum 3:1 contrast ratio
   - Interactive elements: minimum 3:1 contrast ratio
   - Do any elements rely solely on color to convey information?
6. **Prioritized remediation plan.** For each violation:
   - WCAG criterion
   - Severity and customer impact
   - Affected component/page
   - Recommended fix
   - Effort estimate
   - Priority (based on impact and legal risk)

### Amazon Writing Style Rules
- Specific: "The 'Submit' button on /settings/profile has a contrast ratio of 2.8:1 (requires 4.5:1)" not "some buttons have low contrast"
- Data-driven: quantify violations, affected users, and compliance percentage
- No weasel words: "mostly accessible" must become "compliant with 87 of 98 applicable WCAG 2.1 AA criteria (89%)"
- Customer-obsessed: describe impact in terms of what the customer cannot do
- Actionable: every finding has a specific remediation with effort estimate
- "So what": frame compliance gaps in terms of customer exclusion and legal risk

## Output Format
```
Accessibility Audit - <Product/Service> - <Date>
Target: WCAG [version] Level [AA/AAA]

EXECUTIVE SUMMARY
Compliance: [X/Y criteria met] ([Z%])
Critical violations: [N] | Serious: [N] | Moderate: [N] | Minor: [N]
Change since last audit: [+/- N violations]

VIOLATIONS BY CATEGORY
| Category | Critical | Serious | Moderate | Minor | Total |
|----------|----------|---------|----------|-------|-------|
| Perceivable | ... | ... | ... | ... | ... |
| Operable    | ... | ... | ... | ... | ... |
| Understandable | ... | ... | ... | ... | ... |
| Robust      | ... | ... | ... | ... | ... |

SCREEN READER ISSUES
| # | Page/Component | Issue | Impact | WCAG Criterion | Fix |
|---|---------------|-------|--------|---------------|-----|
| 1 | ...           | ...   | ...    | ...           | ... |

KEYBOARD NAVIGATION ISSUES
| # | Page/Component | Issue | Impact | WCAG Criterion | Fix |
|---|---------------|-------|--------|---------------|-----|
| 1 | ...           | ...   | ...    | ...           | ... |

COLOR CONTRAST ISSUES
| # | Element | Current Ratio | Required | Page | Fix |
|---|---------|--------------|----------|------|-----|
| 1 | ...     | ...          | ...      | ...  | ... |

REMEDIATION PLAN
| Priority | Issue | WCAG | Component | Fix | Effort | Sprint |
|----------|-------|------|-----------|-----|--------|--------|
| P0       | ...   | ...  | ...       | ... | ...    | ...    |
| P1       | ...   | ...  | ...       | ... | ...    | ...    |

PROGRESS SINCE LAST AUDIT
| Fixed | New | Net Change | Compliance Trend |
|-------|-----|-----------|-----------------|
| ...   | ... | ...       | ...             |
```

## Delivery
Save as audit report document. Send Slack DM to engineering lead and accessibility champion with summary and P0 items. File Taskei tickets for P0 and P1 items with appropriate priority.
