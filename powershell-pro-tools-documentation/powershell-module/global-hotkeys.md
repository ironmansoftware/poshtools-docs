---
description: Global hotkeys for invoking PowerShell with keystrokes.
---

# Global Hotkeys

{% hint style="info" %}
Global Hotkeys are only supported on Windows. 
{% endhint %}

Global hotkeys allow you to assign hotkeys to PowerShell script blocks. You have access to the current foreground window and process so you can customize your hotkey actions based on what window is open. 

## Defining a Hotkey

You can define hot keys using `Set-Hotkey`. This cmdlet allows you to specify the action to execute and the modifiers and key to invoke the action.

In the example, pressing `Ctrl+B` will open notepad. 

```text
Set-Hotkey -Action { Start-Process Notepad } -ModifierKeys Ctrl -Key B
```

### Passing Variables

You can pass variables to actions just by defining them in the parent scope.

```text
$Process = "Notepad"
Set-Hotkey -Action { Start-Process $Process } -ModifierKeys Ctrl -Key B
```

### Accessing Foreground Window and Process Information

You can access the foreground window title and process information by using the `$args` variable. The first argument it the foreground window title and the second argument is the process object for that window. 

This example will write the foreground window title to the console. 

```text
Set-Hotkey -Action { Write-Host $args[0] } -ModifierKeys Ctrl -Key B
```

This example will open another instance of the selected process. The second argument is a [Process class](https://docs.microsoft.com/en-us/dotnet/api/system.diagnostics.process?view=net-5.0).

```text
Set-Hotkey -Action { Start-Process $args[1].Path } -ModifierKeys Ctrl -Key B
```

## Retrieving Hotkeys

You can use `Get-Hotkey` to retrieve hotkeys that have been defined. 

```text
PS C:\Users\adamr> Get-Hotkey

Action                        ModifierKeys Keys
------                        ------------ ----
 Start-Process $args[1].Path          Ctrl    B
```

## Removing Hotkeys

You can remove hotkeys using `Remove-Hotkey`. 

```text
Get-Hotkey | Remove-Hotkey
```

