# About Cron Jobs
Cron is a time-based job scheduler in Unix-like operating systems, including Linux. It allows you to automate repetitive tasks by scheduling them to run at specific intervals.

# Scheduling a Cron Job with `crontab`
1. Open a terminal window.
- To open your current cron jobs: `crontab -e`
2. To edit your user's crontab, type:
   This will open the default text editor (usually vi or nano) with your crontab file.
3. In the editor, add a new line for your cron job. Each line represents a single cron job entry.
4. The general syntax of a cron job entry is as follows:
   The five asterisks represent the time and date fields.
   - The first field represents minutes (0-59)
   - The second field represents hours (0-23)
   - The third field represents days of the month (1-31)
   - The fourth field represents months (1-12)
   - The fifth field represents days of the week (0-6, where 0 is Sunday and 6 is Saturday)
5. After adding the desired cron job(s), save the file and exit the text editor.

# Additional Commands
- To list your current cron jobs: `crontab -l`
- To remove your crontab: `crontab -r`
