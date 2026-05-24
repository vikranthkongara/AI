# Cost Monitoring Report

Track AWS cost trends for team-owned resources, detect anomalies, identify unused resources, and surface optimization opportunities. Helps stay within budget and demonstrate responsible resource stewardship to leadership.

## Data Sources
- AWS Cost Explorer: cost and usage data by service, resource, tag
- Apollo: deployed services and their resource footprint
- Pipelines: environment configurations (dev/staging/prod resource allocations)
- Taskei: cost optimization tickets, budget-related tasks
- CloudWatch: utilization metrics for right-sizing analysis
- Email (Outlook): AWS budget alerts, cost anomaly notifications

## Instructions

1. Pull cost data for all resources tagged to the team (past 30 days, with month-over-month comparison):
   - Total spend by AWS service (EC2, Lambda, S3, DynamoDB, etc.)
   - Cost per team-owned service/application
   - Cost per environment (production, staging, development, test)
   - Daily cost trend (identify spikes)
   - Forecasted month-end spend vs budget

2. Anomaly detection:
   - Identify any day where spend exceeded 2x the 30-day average
   - Spot new cost categories that appeared this month
   - Flag resources with cost growth > 20% month-over-month
   - Check for cost spikes correlating with deployments (check Pipelines)

3. Identify unused or underutilized resources:
   - EC2 instances with < 10% average CPU utilization
   - EBS volumes not attached to any instance
   - Unattached Elastic IPs
   - S3 buckets with no access in 90+ days
   - DynamoDB tables with provisioned capacity far exceeding actual usage
   - Lambda functions not invoked in 30+ days
   - Load balancers with no healthy targets
   - Development/test environments running 24/7 that could be scheduled

4. Right-sizing opportunities:
   - EC2 instances that could be downsized based on utilization
   - DynamoDB tables that could switch to on-demand pricing
   - S3 storage classes that could be optimized (Infrequent Access, Glacier)
   - Reserved Instance/Savings Plan coverage gaps or upcoming expirations

5. Compare against budget:
   - Current spend vs allocated budget (% utilized)
   - Projected over/under for the quarter
   - New resources added this month and their cost impact
   - Cost savings achieved from optimization work this quarter

6. Environment cost analysis:
   - Non-production environments as % of total (target: < 30%)
   - Dev/test resources that mirror production unnecessarily
   - Environments that could be torn down after hours

## Output Format

```
## Cost Monitoring Report
**Period:** [month/date range]
**Team:** [team name]
**Total Spend:** $[amount] ([+/- %] vs last month)
**Budget Status:** $[spent] / $[budget] ([%] utilized, [n] days remaining)
**Projected Month-End:** $[forecast] ([over/under budget by $X])

---

### Cost Trend (Past 30 Days)
- Average daily spend: $[amount]
- Peak day: [date] at $[amount] (reason: [if identifiable])
- Lowest day: [date] at $[amount]
- Trend: [increasing/stable/decreasing] at [rate]

---

### Cost by Service

| AWS Service | This Month | Last Month | Change | % of Total |
|-------------|-----------|-----------|--------|------------|
| [service]   | $[amount] | $[amount] | [+/-%] | [%]        |
| **Total**   | **$[amount]** | **$[amount]** | **[+/-%]** | **100%** |

---

### Cost by Application

| Application | Environment | Monthly Cost | Trend | Per-Request Cost |
|-------------|------------|-------------|-------|-----------------|
| [app]       | prod       | $[amount]   | [trend] | $[amount]     |
| [app]       | dev/test   | $[amount]   | [trend] | N/A           |

---

### Anomalies Detected

| Date | Service/Resource | Expected | Actual | Excess | Likely Cause |
|------|-----------------|----------|--------|--------|--------------|
| [date] | [resource] | $[amount] | $[amount] | $[amount] | [cause] |

---

### Optimization Opportunities

| # | Opportunity | Current Cost | Projected Savings | Effort | Action |
|---|------------|-------------|-------------------|--------|--------|
| 1 | [e.g., "Right-size i3.xlarge to i3.large"] | $[/mo] | $[/mo] ([%]) | [Low/Med/High] | [specific action] |
| 2 | [e.g., "Delete unused EBS volumes"] | $[/mo] | $[/mo] | Low | [action] |
| 3 | [e.g., "Schedule dev env off-hours"] | $[/mo] | $[/mo] | Medium | [action] |

**Total potential monthly savings:** $[amount] ([%] of current spend)

---

### Unused Resources (Candidates for Deletion)

| Resource | Type | Region | Last Activity | Monthly Cost | Owner |
|----------|------|--------|--------------|-------------|-------|
| [ID]     | [type] | [region] | [date/Never] | $[amount] | [who created it] |

---

### Savings Achieved This Quarter
- Optimizations completed: [n]
- Monthly savings realized: $[amount]
- Annualized savings: $[amount]
- Key wins: [list]

---

### Recommendations
1. **Quick wins (this week):** [delete unused resources, estimated savings: $X/mo]
2. **This sprint:** [right-sizing changes, estimated savings: $X/mo]
3. **Next quarter:** [architectural changes for cost efficiency]
4. **Budget action:** [if trending over budget, suggest where to cut]
```

## Delivery
Send the formatted report as a Slack DM to me. If spend is projected to exceed budget by more than 10%, flag this as URGENT at the top with specific recommendations on what to cut or defer. Run this report weekly.
