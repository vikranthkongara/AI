# Setup Daily Manager Cron

Set up a recurring MeshClaw cron job that runs my daily manager briefing automatically every weekday morning.

Use `cron_add` to schedule the following job:

- **Name:** daily-manager-briefing
- **Schedule:** Every weekday at 8:30 AM (Mon-Fri)
- **Task:** Run the full daily manager workflow:

1. Check emails from the last 12 hours. For important ones (escalations, action items, leadership asks, approvals needed, incident notifications), send a Slack DM summary with subject, sender, 1-2 line summary, and urgency level (🔴/🟡/🟢). Skip newsletters and automated noise.

2. Check unread Slack DMs. Send a consolidated Slack DM listing who messaged me and what they need.

3. Check today's calendar for any meetings added in the last 24 hours. Send a Slack DM alert for each last-minute invite.

4. For any 1:1 meetings today, look up the person's recent CRs, Taskei tasks, and blockers. Send a prep summary Slack DM with their activity, blocked items, and suggested talking points. Time this 30 minutes before each 1:1.

Use `session="origin"` for send_message so results appear in my dashboard.
