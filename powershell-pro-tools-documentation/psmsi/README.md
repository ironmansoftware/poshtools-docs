# PSMSI

PSMSI is a PowerShell module for creating MSI installers from PowerShell. It generates WiX XML and runs the WiX Toolset v3 tools that are included with the module.

Use PSMSI when you want to describe installer content, shortcuts, custom actions, and basic installer UI directly in PowerShell.

## Features

* Create MSI packages from files and directories.
* Install per-user or per-machine.
* Add Add/Remove Programs icons.
* Create desktop shortcuts.
* Run PowerShell custom actions during install or uninstall.
* Add basic installer UI with custom EULAs and images.

## Quick Example

```powershell
Install-Module PSMSI

New-Installer -ProductName "My First Product" -UpgradeCode '1a73a1be-50e6-4e92-af03-586f4a9d9e82' -Content {
    New-InstallerDirectory -PredefinedDirectory "LocalAppDataFolder" -Content {
        New-InstallerDirectory -DirectoryName "My First Product" -Content {
            New-InstallerFile -Source .\license.txt
        }
    }
} -OutputDirectory (Join-Path $PSScriptRoot "output")
```

The output directory contains the generated `.wxs`, `.wixobj`, and `.msi` files. Distribute the `.msi` file to users.

## Common Commands

* `New-Installer`
* `New-InstallerDirectory`
* `New-InstallerFile`
* `New-InstallerShortcut`
* `New-InstallerCustomAction`
* `New-InstallerUserInterface`

## More Information

* [Installation](installation.md)
* [System Requirements](system-requirements.md)
* [GitHub](https://github.com/ironmansoftware/psmsi)
* [PowerShell Gallery](https://www.powershellgallery.com/packages/PSMSI)
