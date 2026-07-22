# Directories and Files

Every installer content tree should start with a predefined Windows Installer directory. Use `New-InstallerDirectory -PredefinedDirectoryName` for the root folder, then nest custom directories and files inside it.

```powershell
New-Installer -ProductName "My App" `
    -Manufacturer "Example Company" `
    -UpgradeCode "66ad7f2c-e176-4a91-b73b-5dced490ec67" `
    -Version "1.0.0" `
    -OutputDirectory ".\output" `
    -Content {
        New-InstallerDirectory -PredefinedDirectoryName "ProgramFilesFolder" -Content {
            New-InstallerDirectory -DirectoryName "My App" -Id "INSTALLFOLDER" -Content {
                New-InstallerFile -Source ".\bin\MyApp.exe" -Id "MyAppExe"
                New-InstallerFile -Source ".\bin\MyApp.dll"
                New-InstallerFile -Source ".\README.txt"
            }
        }
    } `
    -RequiresElevation
```

Use `-Id` when another installer item needs to reference the directory or file. If you do not provide an ID, PSMSI generates one.

`New-InstallerFile` accepts pipeline input, so you can add a group of files to the current directory.

```powershell
Get-ChildItem ".\assets\*.png" | New-InstallerFile
```

Use `-Configurable` on one custom directory when the user should be able to choose the install location.

```powershell
New-InstallerDirectory -PredefinedDirectoryName "LocalAppDataFolder" -Content {
    New-InstallerDirectory -DirectoryName "My App" -Id "INSTALLFOLDER" -Configurable -Content {
        New-InstallerFile -Source ".\MyApp.exe" -Id "MyAppExe"
    }
}
```

Only one configurable directory is supported.
