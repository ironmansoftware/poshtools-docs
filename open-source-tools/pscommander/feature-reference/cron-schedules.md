# CRON Schedules

PSCommander allows you to run script blocks based on CRON schedules. PSCommander uses a single runspace, so long running scripts are not recommended.

To create a CRON schedule, use `New-CommanderSchedule` within `config.ps1`. This configuration opens Notepad every minute.

You can use a site like [crontab guru](https://crontab.guru/) to define schedules.

```powershell
New-CommanderSchedule -CronExpression "* * * * *" -Action {
     Start-Process Notepad
}
```
