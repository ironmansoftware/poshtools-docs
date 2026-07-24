---
description: Command your desktop with PSCommander.
---

# PSCommander

PSCommander is a Windows desktop automation module. It lets you define PowerShell script blocks for Windows integration points such as hot keys, tray menus, schedules, Explorer context menus, file associations, custom protocol handlers, and desktop widgets.

Use PSCommander when you want persistent desktop automation that is configured with PowerShell.

## Features

* [CRON schedules](feature-reference/cron-schedules.md).
* [Desktop shortcuts](feature-reference/desktop-shortcuts.md).
* [Desktop widgets](feature-reference/desktop-widgets/README.md).
* [Data sources for widgets](feature-reference/data-sources.md).
* [Windows and PSCommander events](feature-reference/events.md).
* [Explorer context menus](feature-reference/explorer-context-menus.md).
* [File associations](feature-reference/file-associations.md).
* [Custom protocol handlers](feature-reference/custom-protocol-handlers.md).
* [Global hot keys](feature-reference/global-hot-keys.md).
* [Tray icon and menus](feature-reference/tray-icon-and-menu.md).

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

See [Configuration](configuration.md) for more information.

## More Information

* [Changelog](https://github.com/ironmansoftware/pscommander/releases)
* [Installation](installation.md)
* [System Requirements](system-requirements.md)
* [Configuration](configuration.md)
* [Feature Reference](feature-reference/README.md)
* [GitHub](https://github.com/ironmansoftware/pscommander)
* [PowerShell Gallery](https://www.powershellgallery.com/packages/PSCommander)
