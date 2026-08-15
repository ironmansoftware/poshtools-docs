# Per-User and Per-Machine Installs

By default, PSMSI creates a per-user installer. A common per-user target is `LocalAppDataFolder`.

```powershell
New-InstallerDirectory -PredefinedDirectoryName "LocalAppDataFolder" -Content {
    New-InstallerDirectory -DirectoryName "My App" -Content {
        New-InstallerFile -Source ".\MyApp.exe"
    }
}
```

For an all-users installer, install under a machine-wide folder such as `ProgramFilesFolder` and add `-RequiresElevation` to `New-Installer`.

```powershell
New-Installer -ProductName "My App" `
    -UpgradeCode "66ad7f2c-e176-4a91-b73b-5dced490ec67" `
    -OutputDirectory ".\output" `
    -RequiresElevation `
    -Content {
        New-InstallerDirectory -PredefinedDirectoryName "ProgramFilesFolder" -Content {
            New-InstallerDirectory -DirectoryName "My App" -Content {
                New-InstallerFile -Source ".\MyApp.exe"
            }
        }
    }
```

The person installing a per-machine MSI needs administrative permissions.
