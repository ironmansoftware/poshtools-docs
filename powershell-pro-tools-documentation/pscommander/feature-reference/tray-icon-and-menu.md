# Tray Icon and Menu

PSCommander provides configuration for the tray icon. You can define the hover text and the icon that is displayed. You can choose to hide the Exit and Edit Config options and define your own right click menus.

Tray menu items can invoke script actions and you can define menu items dynamically. This example creates some menu items statically and dynamically.

```powershell
New-CommanderToolbarIcon -MenuItem @(
    New-CommanderMenuItem -Text 'Notepad' -Action {
        Start-Process notepad
    } -MenuItem @(
        New-CommanderMenuItem -Text 'Subnotepad' -Action {
            Start-Process notepad
        }
    ) -LoadMenuItems {
        New-CommanderMenuItem -Text 'Dynamic SubNotepad' -Action {
            Start-Process notepad
        }
    }
) -LoadMenuItems {
    New-CommanderMenuItem -Text 'Dynamic Notepad' -Action {
        Start-Process notepad
    }
}
```
