# Desktop Shortcuts

PSCommander can create desktop shortcuts that will execute PowerShell when clicked. Desktop shortcuts require that PSCommander is running, so you may want to use `Install-Commander` to ensure that it has been started before a user clicks a shortcut.

You can configure the text, description and icon for the shortcut. This example creates a desktop shortcut that opens Notepad when clicked.

```powershell
New-CommanderShortcut -Text 'Click Me' -Description 'Nice' -Action {
    Start-Process notepad
}
```
