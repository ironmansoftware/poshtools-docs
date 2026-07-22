# Installer UI

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
