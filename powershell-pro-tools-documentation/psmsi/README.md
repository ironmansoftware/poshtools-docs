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

## Install

```powershell
Install-Module PSMSI
Import-Module PSMSI
```

Use `-Scope CurrentUser` when you do not want to install the module for all users.

```powershell
Install-Module PSMSI -Scope CurrentUser
```

## Quick Start

Create a build script, place the files you want to install next to the script, and run the script from PowerShell.

```powershell
$OutputDirectory = Join-Path $PSScriptRoot "output"
$LicensePath = Join-Path $PSScriptRoot "license.txt"

New-Installer -ProductName "My First Product" `
    -Manufacturer "Example Company" `
    -UpgradeCode "1a73a1be-50e6-4e92-af03-586f4a9d9e82" `
    -Version "1.0.0" `
    -OutputDirectory $OutputDirectory `
    -Content {
        New-InstallerDirectory -PredefinedDirectoryName "LocalAppDataFolder" -Content {
            New-InstallerDirectory -DirectoryName "My First Product" -Content {
                New-InstallerFile -Source $LicensePath
            }
        }
    }
```

The output directory contains the generated `.wxs`, `.wxsobj`, and `.msi` files. The `.msi` file is the installer you distribute. The other files are WiX build artifacts that are useful when troubleshooting installer generation.

## Installer Identity

`New-Installer` defines the MSI package and runs the WiX build. These parameters are the ones you will usually set first.

* `ProductName` is required and appears in the installer and Add/Remove Programs.
* `UpgradeCode` is required. Generate it once for a product and keep it the same for every release of that product.
* `Version` defaults to `1.0`. Increase it when shipping upgrades. Windows Installer blocks downgrades.
* `ProductId` defaults to `*`, which lets Windows Installer generate a new product code for the package.
* `Manufacturer` defaults to `Ironman Software, LLC`; set it to your organization for published installers.
* `OutputDirectory` is required and receives the MSI and WiX build artifacts.
* `Platform` defaults to `x86` and accepts `x86`, `x64`, `ia64`, `arm`, `intel`, or `intel64`.
* `Description`, `HelpLink`, `AboutLink`, and `AddRemoveProgramsIcon` add installer metadata.

Generate an upgrade code once and store it in your build script or build configuration.

```powershell
New-Guid
```

Do not call `New-Guid` inside the installer build for `UpgradeCode` after your first release. Changing the upgrade code makes Windows Installer treat the MSI as a different product.

## Directories And Files

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

## Per-User And Per-Machine Installs

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

## Shortcuts

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

## Custom Actions

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

## Installer UI

Use `New-InstallerUserInterface` to create UI options, then pass them to `New-Installer -UserInterface`.

```powershell
$UserInterface = New-InstallerUserInterface `
    -Eula ".\eula.rtf" `
    -TopBanner ".\banner.png" `
    -WelcomeAndCompletionBackground ".\welcome.png" `
    -ExitDialogText "My App has been installed."

New-Installer -ProductName "My App" `
    -UpgradeCode "66ad7f2c-e176-4a91-b73b-5dced490ec67" `
    -OutputDirectory ".\output" `
    -UserInterface $UserInterface `
    -Content {
        New-InstallerDirectory -PredefinedDirectoryName "LocalAppDataFolder" -Content {
            New-InstallerDirectory -DirectoryName "My App" -Content {
                New-InstallerFile -Source ".\MyApp.exe"
            }
        }
    }
```

Recommended image sizes are:

* `TopBanner`: 493 by 58 pixels.
* `WelcomeAndCompletionBackground`: 493 by 312 pixels.
* `ExclamationIcon`: 32 by 32 pixels.
* `InformationIcon`: 32 by 32 pixels.
* `NewIcon`: 16 by 16 pixels.
* `UpIcon`: 16 by 16 pixels.

PSMSI warns when a referenced UI file is missing or when an image does not match the recommended size.

## Command Reference

| Command | Purpose |
| --- | --- |
| `New-Installer` | Creates the MSI and writes the `.wxs`, `.wxsobj`, and `.msi` files to the output directory. |
| `New-InstallerDirectory` | Adds a predefined or custom directory to the installer content tree. |
| `New-InstallerFile` | Adds a file to the current installer directory. |
| `New-InstallerShortcut` | Adds a shortcut to a file or directory. |
| `New-InstallerCustomAction` | Defines a PowerShell custom action for install or uninstall. |
| `New-InstallerUserInterface` | Defines EULA, image, icon, and completion text options for the installer UI. |

## Troubleshooting

* Use `-Verbose` on `New-Installer` to see WiX compiler and linker output.
* Verify every file referenced by `New-InstallerFile`, `AddRemoveProgramsIcon`, shortcut icons, and UI parameters exists before building.
* Keep file and directory IDs unique when you specify them manually.
* Use a stable `UpgradeCode` and increase `Version` for upgrade releases.
* Use `-RequiresElevation` for installers that write to protected machine locations such as Program Files.
* Inspect the generated `.wxs` file when WiX reports validation or linking errors.

## More Information

* [Installation](installation.md)
* [System Requirements](system-requirements.md)
* [GitHub](https://github.com/ironmansoftware/psmsi)
* [PowerShell Gallery](https://www.powershellgallery.com/packages/PSMSI)
