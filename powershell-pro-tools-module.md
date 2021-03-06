---
description: Changelog for the PowerShell Pro Tools PowerShell module.
---

# PowerShell Pro Tools Module

## 5.8.0 - 3-1-2021

* Added support for building .NET Core based Windows Services with PowerShell 7

## 5.7.5 - 2-11-2021

* Fixed an issue where packaging would not work with modules that contained a C\# .cs file \(like MSAL.PS\)

## 5.7.4 - 2-9-2021

* Added support for Packaging on Mac OSX

## 5.7.3 - 2-8-2021

* Fixed an issue where arguments would not be passed to packaged scripts running PowerShell 7
* Added support for [Packaging on Linux](powershell-pro-tools-documentation/packaging/packaging-on-linux.md)

## 5.7.2 - 1-15-2021

* Fixed an issue where the license key would always show the incorrect date 
* Updated to the latest version of PSScriptPad.

## 5.7.1 - 12-10-2020

* Fixed an issue where Global Hotkeys could cause the PowerShell process to crash
* Added an -ArgumentList parameter to the Set-HotKey cmdlet

## 5.7.0 - 12-9-2020

* Added support for [Global Hotkeys](powershell-pro-tools-documentation/powershell-module/global-hotkeys.md).

## 5.6.8 - 12-3-2020

* Added support for PowerShell Pro Tools subscriptions

## 5.6.7 - 11-16-2020

* Fixed an issue where the packager could fail when packaging certain Windows PowerShell modules. 

## 5.6.6 - 11-4-2020

* Fixed an issue with packaging the NTFSSecurity module

