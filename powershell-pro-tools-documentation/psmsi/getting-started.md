# Getting Started

Create a build script, place the files you want to install next to the script, and run the script from PowerShell.

```powershell
$OutputDirectory = Join-Path $PSScriptRoot "output"
$ConfigPath = Join-Path $PSScriptRoot "appsettings.json"

New-Installer -ProductName "My First Product" `
    -Manufacturer "Example Company" `
    -UpgradeCode "1a73a1be-50e6-4e92-af03-586f4a9d9e82" `
    -Version "1.0.0" `
    -OutputDirectory $OutputDirectory `
    -Content {
        New-InstallerDirectory -PredefinedDirectoryName "LocalAppDataFolder" -Content {
            New-InstallerDirectory -DirectoryName "My First Product" -Content {
                New-InstallerFile -Source $ConfigPath
            }
        }
    }
```

The output directory contains the generated `.wxs`, `.wxsobj`, and `.msi` files. The `.msi` file is the installer you distribute. The other files are WiX build artifacts that are useful when troubleshooting installer generation.

Use `-Verbose` on `New-Installer` to see the WiX compiler and linker output while the installer is built.
