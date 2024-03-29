# PowerShell Packager

## 2024.3.0 - 3/19/2024

* Fixed an issue with packaging as a service (#3184)

### 2024.1.0 - 1/4/2024

* Added support for signing executables
* Added diagnostic logging
* Fixed an issue with the output pane not scrolling properly.

### 2023.6.0 - 6/20/2023

* Added installation directory selector during upgrade

## 2023.3.0 - 3/14/2023

* Added support for loading package.psd1 files&#x20;

## 2023.2.0 - 2/27/2023

* Fixed an issue where specifying an icon with the IronmanPowerShellHost would cause the executable to fail to run.

## 2023.1.0 - 1/10/2023

* Added support for specifying any .NET or PowerShell 7 version to package
* Fixed an issue where the IronmanPowerShellHost would not accept arguments
* Fixed an issue where the IronmanPowerShellHost would truncate the first 3 characters

## 2022.12.2 - 1/5/2023

* Fixed an issue where the IronmanPowerShellWinFormsHost wouldn't run anything

## 2022.12.1 - 12/17/2022

* Fixed an issue where the Ironman PowerShell Host wouldn't properly set $PSScriptRoot

## 2022.11.3 - 11-29-2022

* Added support for packaging icons

## 2022.11.2 - 11-28-2022

* Fixed an issue where the Require Elevation parameter would not work
* Fixed an issue where modules would not be loaded correctly in packaged executables.
* Fixed an issue where invalid File Versions would cause the packager to fail

## 2022.11.1 - 11-28-2022

* Fixed an issue where the packager would start on Windows startup
* Fixed an issue where the Actipro license was not activated properly

## 2202.11.0 - 11-16-2022

* Initial release
