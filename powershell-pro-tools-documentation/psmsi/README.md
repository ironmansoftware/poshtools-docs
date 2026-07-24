# PSMSI

PSMSI is a PowerShell module for creating Windows MSI installers from PowerShell scripts. It builds WiX XML from cmdlets such as `New-Installer`, `New-InstallerDirectory`, and `New-InstallerFile`, then runs the WiX Toolset v3 compiler and linker that ship with the module.

Use PSMSI when you want a repeatable installer build script for files, folders, shortcuts, simple installer UI customization, and PowerShell custom actions.

## Features

* Create MSI packages from PowerShell build scripts.
* Install files into predefined Windows Installer folders such as `LocalAppDataFolder`, `ProgramFilesFolder`, `ProgramMenuFolder`, and `DesktopFolder`.
* Build per-user installers or per-machine installers that require elevation.
* Create nested application folders and allow one folder to be configurable during install.
* Add Add/Remove Programs metadata, icons, help links, and about links.
* Create file and folder shortcuts with arguments, working directories, icons, and window state.
* Run PowerShell scripts during install or uninstall with custom actions.
* Add a basic installer UI with a EULA, completion text, and custom images.

## Quick Example

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

The output directory contains the generated `.wxs`, `.wxsobj`, and `.msi` files. The `.msi` file is the installer you distribute.

## Feature Guides

* [Getting Started](getting-started.md)
* [Installer Identity](installer-identity.md)
* [Directories and Files](directories-and-files.md)
* [Per-User and Per-Machine Installs](per-user-and-per-machine-installs.md)
* [Shortcuts](shortcuts.md)
* [Custom Actions](custom-actions.md)
* [Installer UI](installer-ui.md)
* [Command Reference](command-reference.md)
* [Troubleshooting](troubleshooting.md)

## More Information

* [Changelog](https://github.com/ironmansoftware/psmsi/releases)
* [Installation](installation.md)
* [System Requirements](system-requirements.md)
* [GitHub](https://github.com/ironmansoftware/psmsi)
* [PowerShell Gallery](https://www.powershellgallery.com/packages/PSMSI)
