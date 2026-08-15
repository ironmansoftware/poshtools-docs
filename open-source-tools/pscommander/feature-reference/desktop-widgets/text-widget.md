# Text Widget

The following example creates a text widget with some computer information.

```powershell
$CI = Get-ComputerInfo

$ComputerInfo = @"
    Number of Processes: $($CI.OsNumberOfProcesses)
    Number of Users: $($CI.OsNumberOfUsers)
    User Name: $($CI.CsUserName)
    System Family: $($CI.CsSystemFamily)
"@

New-CommanderDesktop -Widget @(
   New-CommanderDesktopWidget -Text $ComputerInfo -Height 300 -Width 1000 -FontSize 30 -Top 500 -Left 500 -FontColor 'Black'
)
```
