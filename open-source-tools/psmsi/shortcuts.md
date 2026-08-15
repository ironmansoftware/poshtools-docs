# Shortcuts

Create shortcuts with `New-InstallerShortcut` inside the directory where the shortcut should be installed. Reference an installed file by the file ID.

```powershell
New-Installer -ProductName "My App" `
    -Manufacturer "Example Company" `
    -UpgradeCode "66ad7f2c-e176-4a91-b73b-5dced490ec67" `
    -OutputDirectory ".\output" `
    -Content {
        New-InstallerDirectory -PredefinedDirectoryName "LocalAppDataFolder" -Content {
            New-InstallerDirectory -DirectoryName "My App" -Id "INSTALLFOLDER" -Content {
                New-InstallerFile -Source ".\MyApp.exe" -Id "MyAppExe"
            }
        }

        New-InstallerDirectory -PredefinedDirectoryName "DesktopFolder" -Content {
            New-InstallerShortcut -Name "My App" `
                -FileId "MyAppExe" `
                -Description "Launch My App" `
                -IconPath ".\app.ico" `
                -WorkingDirectoryId "INSTALLFOLDER" `
                -Arguments "--profile default" `
                -Show "normal"
        }
    }
```

`New-InstallerShortcut` can also target a directory with `-DirectoryId`. `-Show` accepts `normal`, `minimized`, or `maximized`.
