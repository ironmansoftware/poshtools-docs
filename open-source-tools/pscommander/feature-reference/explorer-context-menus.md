# Explorer Context Menus

PSCommander can create context menu items that appear when right clicking on folders and files within Windows Explorer. Your script block receives the path to the folder or file via the `$Args[0]` variable.

You can create context menu items that appear on folders or only apply to particular extensions of files.

This example creates a context menu that displays as Click Me and opens VS Code to the file that was clicked.

```powershell
New-CommanderContextMenu -Text 'Click me' -Action {
    Start-Process code -ArgumentList $args[0]
}
```
