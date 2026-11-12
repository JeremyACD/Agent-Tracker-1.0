# Agent Performance Tracker Builder

A web page that builds the monthly **Agent Performance Tracker** workbook for Team Leads from the daily phone, schedule, payroll, and QA reports.

**Open the tool:** use this repository's GitHub Pages link (Settings → Pages shows the address).

Everything runs in the browser. Reports are read on your computer and never uploaded anywhere, so no employee data is stored in this repository or sent to GitHub.

---

## Each update

1. **Open the tool** and drop in:
   - **The current tracker from the Teams channel.** Always include it. It holds the tool's saved data (roster, monthly totals) and the Team Leads' attendance codes.
   - **The new reports.** File names don't matter (Teams and browsers often rename downloads); each file is recognized by its contents: DetailedHistory, UserStateDetail, the schedule (Data-export, one file per week), the Call Review Team Checklist, and Timesheet Entries. A CDR report is optional; it only fills a day missing from DetailedHistory.

   Each file turns green in the checklist once it's recognized. Anything required that's missing shows in red.

2. **Check the roster** only when something changed: a new hire, a departure, a name change, a move to Tier 2, or someone starting or ending extended PTO. Drop in the **Agent and Team Lead roster** (.csv) with the other files to fill in each agent's email, Team Lead, and Team Lead email; anyone listed as a Team Lead is kept off agent tabs automatically. These can also be edited directly in the table.

3. **Click Build tracker**, then **Download**.

4. **Upload the downloaded file to the Teams channel, replacing the current one** (keep the same file name, so everyone's link keeps working).

The tool picks the last complete day automatically: if the reports were pulled while a day was still in progress, that day waits for the next update.

## Starting a new month

When a month is complete, step 1 shows **Start [next month]**. Click it, then build. This creates a new file for the new month (keep the previous month's file as it is). Quarter-to-date and year-to-date totals carry forward automatically.

Weeks run Sunday to Saturday. A month that begins mid-week starts on the Sunday before the 1st, and the previous month ends the Saturday before, so no week is split or counted twice. January always starts on 1/1 so each year's totals stay separate.

## Messages after a build

| Message | What to do |
|---|---|
| A day "looks partial" | Normal. It will be included next time. |
| Names in the reports that aren't on the roster | Choose **New agent**, **Same person as…** (a name change or different spelling), or **Ignore** (not an agent) under step 2, then build again. |
| Time zone not yet confirmed | Normal for new hires and agents on PTO. It confirms after a few days of timesheet punches. |
| QA checklist: a call date is in the future | A typo in the checklist; the tool used the review date. Worth passing to the checklist owner. |
| Team Lead attendance codes: N new | Lists the PTO, tardy, and absence codes Team Leads entered since the last build. All are kept. |
| Build stopped | The message says which file is missing or unreadable. Add or replace it and build again. |

## Safety net

**Download a backup of the saved data** (bottom of the page) saves the tool's memory as a small `.json` file. If a tracker file is ever lost or overwritten, drop that backup in with the reports to restore it. The backup contains agent names, so store it in the Teams channel, not here.
