# Events

PSCommander can register event handlers that invoke script blocks based on events happening within your system. Use the `Register-CommanderEvent` cmdlet to listen to these events.

The following example starts Notepad when Commander starts.

```powershell
Register-CommanderEvent -OnCommander Start -Action {
   Start-Process notepad
}
```

You can also listen to events that are happening with Windows using WMI event filters. This example uses the built-in `ProcessStarted` event to run a script block whenever a process is started. The example writes to a file. The `$args[0]` value is the WMI object that was created.

```powershell
Register-CommanderEvent -OnWindows ProcessStarted -Action {
   $Args[0]['Name'] | Out-File C:\users\adamr\desktop\process-name.txt
}
```

To configure a custom WMI event, use the `-WmiEventType` and `-WmiEventFilter` parameters.

```powershell
Register-CommanderEvent -OnWindows WmiEvent -WmiEventType '__InstanceCreationEvent' -WmiEventFilter 'TargetInstance isa "Win32_Process"' -Action {
   $Args[0]['Name'] | Out-File C:\users\adamr\desktop\process-name.txt
}
```
