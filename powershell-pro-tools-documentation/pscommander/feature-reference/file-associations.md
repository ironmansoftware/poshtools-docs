# File Associations

PSCommander allows you to associate files with script blocks defined within the commander configuration. You can define the extension and action to take when the file type is open. You receive the full file path in the `$Args[0]` variable.

This example opens VS Code based on the file that was opened and associates it with the `.ps2` file extension.

```powershell
New-CommanderFileAssociation -Extension ".ps2" -Action {
    Start-Process code -ArgumentList $Args[0]
}
```
