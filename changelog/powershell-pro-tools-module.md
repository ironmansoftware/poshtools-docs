---
description: Changelog for the PowerShell Pro Tools PowerShell module.
---

# PowerShell Pro Tools Module



## 2023.2.0 - 2/27/2023

* Fixed an issue where specifying an icon with the IronmanPowerShellHost would cause the executable to fail to run.

## 2023.1.0 - 1/10/2023

* Added support for specifying any .NET or PowerShell 7 version to package
* Merge-Script now outputs build progress by default
* Fixed an issue where the IronmanPowerShellHost would truncate the first 3 characters
* Fixed an issue where the IronmanPowerShellHost would not accept arguments

## 2022.12.2 - 1/7/2023

* Fixed an issue where the IronmanPowerShellWinFormsHost wouldn't run anything

## 2022.12.1 - 12/17/2022

* Fixed an issue where the Ironman PowerShell Host wouldn't properly set $PSScriptRoot

## 2022.12.0 - 12/13/2022

* Removed features that are now available for free
* Add support for icons in the Ironman Software Host Process

## 2022.11.1 - 11/14/2022

* Fixed an issue where unsigned DLLs were not loaded successfully when packaging executables

## 2022.11.0 - 11-9-2022

* Added Ironman Software Host Process

## 2022.10.0 - 10-11-2022

* Fixed an issue where you couldn't create 2 shortcuts to the same file with New-Installer
* Fixed an issue where bundled assemblies would cause unexpected output in executables

## 2022.9.0 - 9-13-2022

* Added support for packaging PowerShell 7.2.5 and 7.2.6 executables

## 2022.8.0 - 8-9-2022

* Added support for packaging PowerShell 7.2.4 executables

## 2022.7.0 - 7-12-2022

* Fixed an issue where license files were not correctly validated

## 2022.5.0 - 5-10-2022

* Fixed an issue where the link to the docs from Show-PSEditor would end in a 404
* Fixed an issue where ANSI escape characters were shown in Show-PSEditor output
* Added support for packaging PS 7.2.3
* Fixed an issue where non-ASCII characters wouldn't be stored correctly after packaging

## 2022.4.0 - 4-12-2022

* Added support for shortcuts to directories.
* Removed code conversion features
* Added Show-PSEditor
* Added Show-TUIDesigner
* Fixed an issue where PowerShell 7.2 executables would not work as a service
* Fixed an issue where PowerShell 7.x executables would not have an icon
* Fixed an issue where PowerShell 7.x executables would not elevate properly

## 2022.3.0 - 3-8-2022

* Fixed an issue where a script compiled as a service would fail to run
* Fixed an issue where compiling on Linux would fail

## 2022.2.1 - 2-10-2022

* Fixed an issue where obfuscated builds wouldn't work twice
* Fixed an issue where obfuscated Windows PowerShell builds wouldn't execute correctly

## 2022.2.0 - 2-8-2022

* Fixed an issue where packaging for Linux would not work
* Added support for icons in PS7 executables
* Added support for obfuscating PS7 executables

## 2022.1.0 - 1-11-2022

* Fixed an issue where PowerShell 7 executables would not have file properties

## 2021.12.3 - 12-27-2021

* Fixed an issue where packaging a PowerShell 7.2 or later executable could result in a failure to build

## 2021.12.2 - 12-21-2021

* Fixed an issue where an attempt to load missing assemblies would be made.

## 2021.12.1 - 12-17-2021

* Fixed an issue where packaging an executable into an output directory with an apostrophe does not work.
* Fixed an issue where PS7.1 and PS7.2 output directories would contain all unpackaged files

## 2021.12.0 - 12-14-2021

* Added support for packaging PowerShell 7.2 and .NET 6.0 executables
* Added support for renaming the output executable

## 2021.11.0 - 11-9-2021

* Added support for bundling PowerShell 7.1 scripts
* Added the ability to sign executables

## 2021.10.0 - 10-12-2021

* Updated to the latest version of PSScriptPad

## 2021.9.0 - 9-14-2021

* Fixed an MSBuild warning that was shown when compiling on Windows
* Added support for bundling additional XAML files in executables
* Fixed an issue where using the .NET 5 SDK would cause executables to fail to build on Windows
* Added support for switching the .NET SDK used to build executables

## 5.9.3 - 7-27-2021

* Fixed an issue where DataGridView columns could not be added to the form designer

## 5.9.2 - 7-22-2021

* Fixed an issue where the packager would fail when the script name had a space in it

## 5.9.1 - 7-21-2021

* Fixed an issue where an exception could be thrown during packaging.

## 5.9.0 - 7-20-2021

* Added support for bundling resources into executables

## 5.8.11 - 7-8-2021

* Added support for packaging PowerShell 7.0.6

## 5.8.10 - 6-3-2021

* Add support for disabling QuickEdit during packaging
* Fixed an issue with the packager and strings with single quotes

## 5.8.9 - 6-2-2021

* Fixed a packaging issue with concatenated strings and Join-Path

## 5.8.8 - 5-17-2021

* Fixed an issue with running Merge-Script on Linux

## 5.8.5 - 4-23-2021

* Fixed an issue with activation caching
* Fixed an issue with packaging PowerCLI

## 5.8.3 - 4-21-2021

* Fixed an issue where packaging modules could cause an Access Denied error
* Added subscription activation caching to prevent excessive web requests

## 5.8.2 - 4-14-2021

* Fixed an issue where packaging would use the wrong PowerShell version when looking up modules causing certain modules to fail to load

## 5.8.1 - 4-7-2021

* Updated the version of PSScriptPad

## 5.8.0 - 3-1-2021

* Added support for building .NET Core based Windows Services with PowerShell 7

## 5.7.5 - 2-11-2021

* Fixed an issue where packaging would not work with modules that contained a C# .cs file (like MSAL.PS)

## 5.7.4 - 2-9-2021

* Added support for Packaging on Mac OSX

## 5.7.3 - 2-8-2021

* Fixed an issue where arguments would not be passed to packaged scripts running PowerShell 7
* Added support for [Packaging on Linux](../powershell-pro-tools-documentation/packaging/packaging-on-linux.md)

## 5.7.2 - 1-15-2021

* Fixed an issue where the license key would always show the incorrect date
* Updated to the latest version of PSScriptPad.

## 5.7.1 - 12-10-2020

* Fixed an issue where Global Hotkeys could cause the PowerShell process to crash
* Added an -ArgumentList parameter to the Set-HotKey cmdlet

## 5.7.0 - 12-9-2020

* Added support for [Global Hotkeys](../powershell-pro-tools-documentation/powershell-module/global-hotkeys.md).

## 5.6.8 - 12-3-2020

* Added support for PowerShell Pro Tools subscriptions

## 5.6.7 - 11-16-2020

* Fixed an issue where the packager could fail when packaging certain Windows PowerShell modules.

## 5.6.6 - 11-4-2020

* Fixed an issue with packaging the NTFSSecurity module
