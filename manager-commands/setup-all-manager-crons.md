# Setup All Manager Cron Jobs

Set up all recurring manager automation cron jobs via MeshClaw. Create ALL of the following:

## 1. Daily Morning Briefing

Use `cron_add`:
- **Name:** daily-manager-briefing
- **Schedule:** Every weekday at 8:30 AM (Mon-Fri)
- **Task:**
  1. Check emails from last 12 hours. For important ones (escalations, action items, leadership asks, approvals, incidents), send Slack DM with subject, sender, 1-2 line summary, urgency (🔴/🟡/🟢). Skip newsletters and noise.
  2. Check unread Slack DMs. Send consolidated Slack DM listing who messaged and what they need.
  3. Check today's calendar for meetings added in last 24 hours. Slack DM alert for each last-minute invite.
  4. For 1:1 meetings today, look up person's recent CRs, Taskei tasks, blockers. Send prep summary Slack DM 30 min before each 1:1.

## 2. End of Day Recap

Use `cron_add`:
- **Name:** eod-recap
- **Schedule:** Every weekday at 5:30 PM (Mon-Fri)
- **Task:**
  1. Summarize today: emails received needing action (responded vs pending), unanswered Slack DMs, meetings attended.
  2. Open action items: emails needing reply, unanswered DMs, CRs awaiting my review, overdue Taskei items, pending approvals.
  3. Tomorrow preview: calendar with times/attendees, flag conflicts and back-to-backs, note 1:1 prep needed.
  4. Escalations/risks: active incidents, SLA deadlines approaching, overnight deployments, blocked team members waiting on me.
  5. End with "Top 3 things to handle first tomorrow."
  6. Send as one consolidated Slack DM with section headers and bullets.

## 3. Weekend Catchup (Monday Morning)

Use `cron_add`:
- **Name:** weekend-catchup
- **Schedule:** Every Monday at 7:30 AM
- **Task:**
  1. Check all emails from Friday 5 PM through now. For important ones (escalations, SEVs, action items, leadership asks, approvals, pages), send Slack DM with subject, sender, day+time sent, summary, urgency (🔴/🟡/🟢).
  2. Check for SEV/incident activity over the weekend. Send consolidated incident summary — what happened, status, whether I need to act.
  3. Check unread Slack DMs and channel mentions from the weekend. Send consolidated Slack DM prioritized by urgency.
  4. Monday calendar preview: all meetings with times, flag ones added over weekend, include 1:1 prep for early morning meetings.
  5. Send everything as Slack DMs for phone triage.

---

Use `session="origin"` for all send_message calls. After creating all three, run `cron_list` to confirm they're active and report back.
