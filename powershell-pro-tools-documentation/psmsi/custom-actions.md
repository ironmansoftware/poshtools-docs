# Custom Actions

Custom actions run installed PowerShell scripts during install or uninstall. Add the script as an installer file, give it an ID, and pass one or more `New-InstallerCustomAction` results to the `New-Installer -CustomAction` parameter.

```powershell
$CustomActions = @(
    New-InstallerCustomAction -FileId "ConfigureScript" `
        -RunOnInstall `
        -CheckReturnValue `
        -Arguments "-NoProfile -ExecutionPolicy Bypass" `
        -ScriptArguments "-Mode Install"
)

New-Installer -ProductName "My App" `
    -UpgradeCode "66ad7f2c-e176-4a91-b73b-5dced490ec67" `
    -OutputDirectory ".\output" `
    -CustomAction $CustomActions `
    -Content {
        New-InstallerDirectory -PredefinedDirectoryName "ProgramFilesFolder" -Content {
            New-InstallerDirectory -DirectoryName "My App" -Content {
                New-InstallerFile -Source ".\MyApp.exe" -Id "MyAppExe"
                New-InstallerFile -Source ".\Configure.ps1" -Id "ConfigureScript"
            }
        }
    } `
    -RequiresElevation
```

Use `-RunOnInstall` for install-time scripts and `-RunOnUninstall` for uninstall-time scripts. `-Arguments` are passed to `powershell.exe`; `-ScriptArguments` are passed to your script. `-CheckReturnValue` causes the install to fail if the PowerShell process returns a non-zero exit code.

Custom actions are passed to `New-Installer` with `-CustomAction`; do not place `New-InstallerCustomAction` inside the `-Content` script block.
