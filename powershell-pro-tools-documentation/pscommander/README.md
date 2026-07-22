---
description: Command your desktop with PSCommander.
---

# PSCommander

PSCommander is a Windows desktop automation module. It lets you define PowerShell script blocks for Windows integration points such as hot keys, tray menus, schedules, Explorer context menus, file associations, custom protocol handlers, and desktop widgets.

Use PSCommander when you want persistent desktop automation that is configured with PowerShell.

## Features

* CRON schedules.
* Desktop shortcuts.
* Desktop widgets.
* Data sources for widgets.
* Windows and PSCommander events.
* Explorer context menus.
* File associations.
* Custom protocol handlers.
* Global hot keys.
* Tray icon and menus.

## Quick Examples

Install the module and register PSCommander to run at logon.

```powershell
Install-Module PSCommander
Install-Commander
```

Create and open the user configuration file.

```powershell
Start-Commander
```

Add a hot key to `Documents\PSCommander\config.ps1`.

```powershell
New-CommanderHotKey -Key 'T' -ModifierKey 'Ctrl' -Action {
    Start-Process notepad
}
```

Add a tray menu item.

```powershell
New-CommanderToolbarIcon -MenuItem @(
    New-CommanderMenuItem -Text 'Open Notepad' -Action {
        Start-Process notepad
    }
)
```

## Configuration

PSCommander loads its configuration from `Documents\PSCommander\config.ps1`. Add PSCommander commands to that file. Changes to the file are reloaded while PSCommander is running.

## More Information

* [Installation](installation.md)
* [System Requirements](system-requirements.md)
* [Feature Reference](../pscommander.md)
* [GitHub](https://github.com/ironmansoftware/pscommander)
* [PowerShell Gallery](https://www.powershellgallery.com/packages/PSCommander)
