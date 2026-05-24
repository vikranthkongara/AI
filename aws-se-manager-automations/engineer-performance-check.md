# Engineer Performance Daily Check & Inspection

Run a daily performance inspection for my AWS Support Engineering team based on 2026 goals. Do ALL of the following:

## 2026 Engineer Goal Targets

| Metric | Target |
|--------|--------|
| Percentage Positive CCR | 92.5% |
| Customer Facing Time (CFT) | 76.2% |
| Live Contacts Answered | 100% to site by profile goal |
| e-TWFL (Engineer Time with Front Line) | 100% to site by profile goal |
| Missed Contacts | ≤ 1 missed contact per week |
| Mandatory and Security Training | 75% on-time completion |
| Skilling | 100% on-time milestone completion |
| FLS Tooling Adoption (Genie) | 44% case usage rate |

---

## 1. CCR (Customer Contact Rating) Check

Review team's CCR performance:
- Pull each engineer's current Percentage Positive CCR
- Flag anyone trending below 92.5% target
- Identify engineers with negative CCR patterns (3+ negative ratings in past week)
- Note any repeat feedback themes from customer comments
- Send Slack DM summary: engineer name, current %, trend direction (improving/declining), action needed

## 2. Customer Facing Time (CFT) Inspection

Check CFT metrics for each engineer:
- Current CFT percentage vs 76.2% target
- Flag engineers below target — identify if driven by excessive aux time, long breaks, or meeting overload
- Check CCP state patterns — excessive time in non-productive states
- Send Slack DM: engineers below target, gap size, probable cause

## 3. Live Contacts & Missed Contacts

Inspect live contact performance:
- Live Contacts Answered vs site profile goal (target: 100%)
- Missed contacts per engineer this week (target: ≤ 1)
- Flag any engineer with 2+ missed contacts
- Check if missed contacts are during core hours vs edge-of-shift
- Send Slack DM: any misses, who, when, and pattern

## 4. e-TWFL (Engineer Time with Front Line)

Check e-TWFL compliance:
- Each engineer's e-TWFL vs site by profile goal (target: 100%)
- Identify engineers not meeting time-on-queue expectations
- Check if shortfalls are due to training, meetings, or avoidable aux
- Send Slack DM: engineers below target with root cause

## 5. FLS Tooling Adoption (Genie Usage)

Inspect Genie case usage:
- Each engineer's Genie usage rate vs 44% target
- Flag engineers significantly below adoption threshold
- Identify if non-usage is on specific case types vs general avoidance
- Send Slack DM: adoption rates, who needs coaching

## 6. Training & Skilling Status

Check compliance metrics:
- Mandatory and Security Training: who has overdue items (target: 75% on-time)
- Skilling milestones: any upcoming deadlines in next 7 days, any past-due
- Flag engineers at risk of missing milestone completion
- Send Slack DM: overdue trainings, upcoming deadlines, engineers needing follow-up

## 7. Daily Risk Summary

Compile an overall team health snapshot:
- Engineers meeting ALL goals (green)
- Engineers at risk on 1-2 metrics (yellow)
- Engineers below target on 3+ metrics (red)
- Any patterns: new hires ramping, specific shift struggling, profile-specific issues
- Top 3 coaching conversations to prioritize today

---

## Output Format

Send a consolidated Slack DM with:

**Team Scorecard (Today)**
| Engineer | CCR | CFT | Live | e-TWFL | Missed | Genie | Training | Status |
Use checkmarks/X marks for quick scanning.

**Action Items for Today:**
- Numbered list of specific actions (coaching conversations, follow-ups, escalations)

**Trends to Watch:**
- Any week-over-week declining metrics

---

If any data source is unavailable, report what worked and what couldn't be retrieved so I can troubleshoot access.
