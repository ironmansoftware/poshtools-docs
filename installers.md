# Installers

PowerShell Pro Tools includes cmdlets for creating MSI packages that can contain any file and directory structure you wish. It also includes functionality to customize the installer interface by including custom EULAs and images. 

## Getting Started

To get started creating installers with PowerShell Pro Tools, you will need to download the latest version of the PowerShell Pro Tools PowerShell module. This can be installed with `Install-Module`. 

```
Install-Module PowerShellProTools
```

## Creating your first installer

The `New-Installer` cmdlet is used to generate an installer. It can contain directories and files for installation. The first step is to define the basic parameters of your installer. 

The Product and UpgradeCode parameters are required. The UpgradeCode is a GUID that needs to remain the same for each version of your product and should be unique from other products. 

```
New-Installer -Product "My First Product" -UpgradeCode '1a73a1be-50e6-4e92-af03-586f4a9d9e82'
```

Within the Content parameter of the New-Installer cmdlet, you need to include a root directory for installation on the end user's machine. The root directory needs to be a predefined directory. One of the parameter sets on New-InstallerDirectory defines a PredefinedDirectory parameter that you can use to select the target root directory. 

```
New-InstallerDirectory -PredefinedDirectory "LocalAppDataFolder" 
```

You can now optionally specify a nested directory within your root directory. This will be created if it does not exist and removed on uninstall. 

```
New-InstallerDirectory -DirectoryName "My First Product" 
```

Finally, you can include files within your directory. The New-InstallerFile cmdlet accepts a Source parameter with the path to the file you would like to install. 

```
New-InstallerFile -Source .\MyTextFile.txt
```

The full script for this installer looks like this.

```
New-Installer -Product "My First Product" -UpgradeCode '1a73a1be-50e6-4e92-af03-586f4a9d9e82'
 - Content {
    New-InstallerDirectory -PredefinedDirectory "LocalAppDataFolder"  -Content {
       New-InstallerDirectory -DirectoryName "My First Product" -Content {
          New-InstallerFile -Source .\MyTextFile.txt
       }
    }
 } -Output (Join-Path $PSScriptRoot "output")
```

Running the above script will product a WXS, WXSOBJ and MSI file in the output directory. The MSI is the only file that you need to provide to your end users. The WXS and WXSOBJ files are artifacts of the Windows Installer XML Toolkit used to generate these installers.

## Adding a shortcut to the desktop 

Shortcuts can be created in any folder using the `New-InstallerShortcut` cmdlet. To create a shortcut, you need to reference the ID of the file you wish to create a shortcut to. The ID parameter of the `New-InstallerFile` cmdlet is optional. When setting the ID, make sure it is unique within the installer. 

```
New-InstallerFile -Source .\MyTextFile.txt -Id "myTestFile"
```

Next, you can define where to create the shortcut by putting a call to `New-InstallerShortcut` within a `New-InstallerDirectory` context script block.

```
New-InstallerDirectory -PredefinedDirectory "DesktopFolder" -Content {
        New-InstallerShortcut -Name "My Test File" -FileId "myTestFile"
    }
```

## Customizing the User Interface

In addition to defining what can go into an installer, you can also define what options and branding you have for your installer. Options include EULAs and images. Use the `New-InstallerUserInterface` cmdlet to set these properties. The result object can be passed to `New-Installer` with the `UserInterface` parameter. 

 ```
 $UserInterface = New-InstallerUserInterface -Eula (Join-Path $PSScriptRoot 'eula.rtf') -TopBanner (Join-Path $PSScriptRoot "banner.png") -Welcome (Join-Path $PSScriptRoot "welcome.png")
 ``` 