---
description: Changelog for PowerShell Pro Tools for Visual Studio Code
---

# PowerShell Pro Tools for Visual Studio Code

## 5.22.0 - 4-5-2021

* Added 'Open PSCommander Configuration' Command

## 5.21.1 - 3-3-2021

* Added a setting for the license key so that licensing works with Settings Sync. 

## 5.21.0 - 3-1-2021

* Added support for building .NET Core based Windows Services with PowerShell 7

## 5.20.10 - 2-11-2021

* Fixed an issue where packaging would not work with modules that contained a C\# .cs file \(like MSAL.PS\)

## 5.20.9 - 2-9-2021

* Added support for Packaging on Mac OSX

## 5.20.8 - 2-8-2021

* Fixed an issue where arguments would not be passed to packaged scripts running PowerShell 7
* Added support for [Packaging on Linux](powershell-pro-tools-documentation/packaging/packaging-on-linux.md)

## 5.20.7 - 1-31-2021

* Fixed an issue where an error could be shown in the console when navigating PowerShell scripts.

## 5.20.6 - 1-25-2021

* Fixed an issue where an error would be shown when the VS Code automation feature could not connect properly

## 5.20.5 - 1-21-2021

* Fixed an issue where an invalid link would be shown in the hover provider.

## 5.20.4 - 1-14-2021

* Fixed an issue where Generate Proxy Function would run on empty command names and show an error in the terminal
* PSScriptPad now persists loaded WPF assembly locations so they are loaded when the application is restarted

## 5.20.3 - 1-12-2021

* Added toolbox support for the WPF designer in PSScriptPad

## 5.20.2 - 1-11-2021

* Fixed an issue where PSScriptPad could crash when opening a XAML file

## 5.20.1 - 1-10-2021

* Fixed a licensing issue with a 3rd party component

## 5.20.0 - 1-10-2021

* Added support for the [PSScriptPad WPF Designer](powershell-pro-tools-documentation/visual-studio-code/wpf-designer.md)

## 5.19.10 - 1-04-2021

* Fixed an issue where Generate Proxy Function would show errors in the terminal
* Fixed an issue where non-subscription licenses would show they were only licensed for 1 week when this wasn't actually the case. 

## 5.19.9 - 12-31-2020

* Added [Generate Proxy Function ](powershell-pro-tools-documentation/visual-studio-code/refactoring.md#generate-proxy-function)refactoring
* Fixed an issue with convert to $\_ and convert to $PSItem refactorings

## 5.19.8 - 12-28-2020

* Added [Enhanced Hover](powershell-pro-tools-documentation/visual-studio-code/enhanced-hover.md) support
* Fixed an issue where the Variable Explorer would cause a memory leak

## 5.19.7 - 12-27-2020

* Fixed issue with Split Pipeline refactoring changing the functionality of a script
* Added integration into VS Code refactoring provider system
* Added [Convert to $PSItem](powershell-pro-tools-documentation/visual-studio-code/refactoring.md#convert-to-usdpsitem) refactoring
* Added [Convert to $\_](powershell-pro-tools-documentation/visual-studio-code/refactoring.md#convert-to-usd_) refactoring
* Fixed an issue where Split Pipeline would show on one-command pipelines

## 5.19.6 - 12-26-2020

* Added [Split Pipeline ](powershell-pro-tools-documentation/visual-studio-code/refactoring.md#split-pipeline)refactoring
* Added [Introduce Using Namespace ](powershell-pro-tools-documentation/visual-studio-code/refactoring.md#introduce-using-namespace)refactoring

## 5.19.5 - 12-25-2020

* Reorganized tree view providers
* Added Help and Information node
* Fixed an issue where an error could be shown if the tree view was clicked before the extension was fully loaded
* Added options for hiding tree view providers
* Added an option to enable module update checks \(now disabled by default\) as it was slow on many machines

## 5.19.4 - 12-23-2020

* Added support for the PowerShell Preview extension

## 5.19.3 - 12-18-2020

* Added [Reorder Parameters](powershell-pro-tools-documentation/visual-studio-code/refactoring.md#reorder-parameters) 

## 5.19.2 - 12-17-2020

* Added [Generate Function from Usage ](powershell-pro-tools-documentation/visual-studio-code/refactoring.md#generate-function-from-usage)Refactoring

## 5.19.1 - 12-15-2020

* Added [Convert To Multiline Command](powershell-pro-tools-documentation/visual-studio-code/refactoring.md#convert-to-multiline-command) Refactoring

## 5.19.0 - 12-14-2020

* Added [Run in new Terminal](powershell-pro-tools-documentation/visual-studio-code/debugging/start-in-new-terminal.md)
* Added [Refactoring](powershell-pro-tools-documentation/visual-studio-code/refactoring.md)

## 5.18.0 - 12-13-2020

* Fixed an issue where variables wouldn't work in PowerShell 7.1
* Fixed an issue where Out-VSCodeGridView wouldn't work in PowerShell 7.1
* Added a command to insert paths from [Provider Explorer](powershell-pro-tools-documentation/visual-studio-code/powershell-explorer.md#provider-explorer)
* Added a command to view child items of a path in [Provider Explorer](powershell-pro-tools-documentation/visual-studio-code/powershell-explorer.md#provider-explorer)
* Added a command to view item properties in [Provider Explorer](powershell-pro-tools-documentation/visual-studio-code/powershell-explorer.md#provider-explorer)

## 5.17.2 - 12-8-2020

* Fixed an issue where ignored elements were case sensitive 
* Added support for expanding paths in strings
* Added support for ignoring paths 

## 5.17.1 - 12-7-2020

* Fixed an issue where RapidSense wouldn't refresh caches after changing settings
* Added Ignored Variables setting to RapidSense
* Fixed an issue where the PowerShell Pro Tools module wouldn't be imported correctly

## 5.17.0 - 12-6-2020

* Added [RapidSense](powershell-pro-tools-documentation/visual-studio-code/rapidsense.md)

## 5.16.11 - 12-5-2020

* Fixed an issue where the profiler failing to return results
* Added millisecond timing to the profiler

## 5.16.10 - 12-3-2020

* Added support for PowerShell Pro Tools subscriptions

## 5.16.9 - 12-2-2020

* Changed purchasing links to point to new store
* Fixed an issue where collections would not expand correctly.

## 5.16.7 - 11-21-2020

* Added support for [scoped package.psd1 files](powershell-pro-tools-documentation/visual-studio-code/packaging-in-visual-studio-code.md#scoped-package-psd1)

## 5.16.6 - 11-16-2020

* Fixed an issue where the packager could fail when packaging certain Windows PowerShell modules. 

## 5.16.5 - 11-09-2020

* Fixed an issue where the PoshTools extension would fail to load if the user profile contained spaces.

## 5.16.4 - 11-4-2020

* Fixed an issue with packaging the NTFSSecurity module

## 5.16.3 - 10-30-2020

* Fixed an issue where the packager would state that there was unreachable code detected

## 5.16.2 - 10-28-2020

**Changed**

* Fixed an issue where the profile would run within the PoshTools host process rather than in the PowerShell process. 

## 5.16.1 - 10-26-2020

**Changed**

* Fixed an issue where packaging would fail with a duplicate assembly error 

### 5.16.0 - 10-20-2020

**Added**

* Added support for Mac OS

### 5.15.4 - 10-15-2020

**Changed**

* Fixed an issue with bundling modules that contained System.Management.Automation.dll
* Fixed an issue with bundling modules that contained RootModules nested in a folder

### 5.15.2 - 9-29-2020

**Changed**

* Fixed an issue in PSScriptPad where variables would not be shown during debugging. 

### 5.15.1 - 9-28-2020

**Changed**

* Fixed an issue with bundling the ActiveDirectory module in PowerShell 7 standalone executables

### 5.15.0 - 9-21-2020

**Added**

* Support for Linux

### 5.14.1 - 9-17-2020

**Changed**

* Fixed an issue with packaging Windows Forms applications with PS7

### 5.14.0 - 9-16-2020

**Added**

* Added support for packaging the 7.0.2 and 7.0.3 PowerShell SDK

### 5.13.1 - 9-13-2020

**Changed**

* Default install of trial license

### 5.13.0 - 9-1-2020

**Added**

* Added "Generate Tool" command

### 5.12.11 – 9-1-2020

**Changed**

* Updated to the latest version of PSScriptPad
* Fixed an issue with Form Generation where it would generate forms with common parameters

### 5.12.10 – 7-21-2020

**Added**

* PowerShell Pro Tools: Install PowerShell Pro Tools Module command

**Changed**

* Fixed an issue that would cause the extension to delay on startup and occasionally time out

### 5.12.9 – 7-16-2020

**Changed**

* Fixed an issue with PSScriptPad where the variables window wouldn’t expand variables correctly

### 5.12.8 – 7-15-2020

**Changed**

* Fixed an issue that would cause a delay on start up

### 5.12.5 – 7-12-2020

**Changed**

* Fixed an issue where ListView, TreeView and ContextMenu child items would not work in PSScriptPad
* VS Code extension now installs the PowerShell module automatically so it loads correctly
* Fixed an issue where packaging would fail if a script ended in a comment
* Fixed an issue where packaging would fail if a script was too large
* Fixed an issue where the opacity setting wouldn’t work on form controls on certain systems.

### 5.12.5 – 7-01-2020

**Changed**

* Fixed an issue where the PowerShell Pro Tools host process could lock up
* Fixed an issue where installing a license would report failure when it was actually succeeding.

### 5.12.4 – 6-26-2020

**Changed**

* Changed the license notification text and link as new licenses have been deployed to all affected customer’s accounts
* Fixed an issue where launching more than one version of VS Code would cause the extension to fail to connect

### 5.12.3 – 6-24-2020

**Changed**

* Fixed an issue where the extension could fail to connect to the PowerShell process.

### 5.12.2 – 6-23-2020

**Changed**

* The provider tree view now runs within the main runspace.

### 5.12.1 – 6-19-2020

**Added** 

* Added Host Processes tree node with support for one-click debugging runspaces

### 5.12.0 – 6-19-2020

**Added** 

* Added an Output Channel for PowerShell Pro Tools diagnostics

**Changed**

* PowerShell Pro Tools now uses an external process rather than being hosted directly in PowerShell
* Fixed an issue where the PowerShell Pro Tools module would load over and over again
* Fixed an issue where the variable window would not show variables
* Fixed an issue with the form designer that wouldn’t be marked dirty when properties were edited
* Fixed an issue with the form designer where it wouldn’t save StatusStrip items
* Fixed an issue with the form designer where it wouldn’t change the main PS1’s form name if it was changed in the designer
* Fixed an issue with the profiler where it would not work if params or using statements were used.

### 5.11.0 – 5-29-2020

**Added**

* Added support for packaging PowerShell 7 executables
* Added experimental support for packaging Linux and OSX executables

### 5.10.1 – 5-6-2020

**Changed**

* Fixed an issue with PSScriptPad that was causing hangs when running WinForm scripts.

### 5.10.0 – 4-17-2020

**Added**

* Out-VSCodeGridView

### 5.9.0 – 4-16-2020

**Added** 

* Cmdlets for managing [VS Code with PowerShell](https://ironmansoftware.com/automating-visual-studio-code-with-powershell/)

### 5.8.8 – 4-14-2020

**Changed**

* Fixed an issue with the variables view showing incorrect child items
* Improved the expansion of child items in the variables view
* Improved the generation of child item paths

### 5.8.7 – 4-6-2020

**Changed**

* Fixed an issue where putting an apostrophe in a label would cause the Form Designer to fail to load
* Fixed an issue where copy and pasting text into PSScriptPad would cause it to crash

### 5.8.6 – 4-3-2020

**Changed**

* Fixed an issue with the variable view not showing variables.

### 5.8.5 – 3-27-2020

**Added**

– Added a $Service object to OnStart\OnStop for packaged services to access the ServiceBase for the service  
– Added $ProcessArgs and $ServiceArgs variables to the runspace for packaged services

**Changed**

– Fixed an issue where $PSScriptRoot would not work for packaged services

### 5.8.4 – 3-3-2020

#### Changed

– Fixed an issue where an error would be shown when loading the extension– Fixed an error where loading the module tree would cause the extension to become unresponsive

### 5.8.3 – 2-10-2020

#### Changed

– Fixed an issue where a failed packaging build would not show the error message in the output

### 5.8.2 – 1-31-2020

#### Added

– Added -ProductId to New-Installer  
– Added -ScriptArguments to New-InstallerCustomAction  
– Added an option to add a context menu item for opening PS1 files with PSScriptPad  
– Added support for Comment \(Ctrl+K,Ctrl+C\) and Uncomment \(Ctrl+K,Ctrl+U\) keyboard shortcuts in PSScriptPad  
– Added support for reloading files updated outside of PSScriptPad

#### Changed

– Fixed issue with installer shortcuts throwing an exception if a workingDirectory or arguments were not specified  
– Fixed an issue where the installer shortcut working directory would not be specified correctly  
– Fixed an issue where the installer shortcut would not use the correct PowerShell variable  
– Fixed an issue where adding images to the installer UI on Windows PowerShell would throw an exception  
– Fixed an issue where PSScriptPad would crash on startup.

### 5.8.1 – 1-28-2020

#### Added

– Added support for WorkingDirectory on New-InstallerShortcut  
– Added support for Arguments on New-InstallerShortcut  
– Added support for Show on New-InstallerShortcut  
– Added support for Arguments on New-InstallerCustomAction

#### Changed

– Fixed issue where packaged applications wouldn’t work with arguments with spaces  
– Fixed issue with installer cmdlets not resolving paths correctly  
– When specifying a shortcut for an installer, if it’s a PS1, it will automatically launch PowerShell.exe rather than targeting the script

### \[5.8.0\] – \(1-22-2020\)

#### Changed

* No longer requires a [trial key](https://ironmansoftware.com/simplifying-product-trial-licensing/)

### \[5.7.1\] – \(1-21-2020\)

#### Changed

* PowerShellProTools module is now signed
* Fixed an issue with [PSScriptPad](https://ironmansoftware.com/psscriptpad/) that was preventing typing while IntelliSense was running in the terminal

### \[5.7.0\] – \(1-18-2020\)

#### Added

* Support for generating resources such as images and icons for WinForms.

#### Changed

* Fixed issue with packaging resources used for WinForms.

### \[5.6.6\] \(1-15-2020\)

#### Changed

* Fixed an issue where licensing would attempt to activate more than once and sometimes failing which resulted in some users not being able to use the tools.

### \[5.6.5\] \(1-14-2020\)

#### Changed

* Fixed an issue where packaging config would not respect the platform property.

### \[5.6.4\] \(1-13-2020\)

#### Changed

* Fixed an issue where packaging would use a package.psd1 in the temp directory.

### \[5.6.3\] \(1-12-2020\)

#### Changed

* Fixed an issue where packaging would throw an invalid format exception
* Fixed an issue with package architecture

### \[5.6.2\] \(1-10-2020\)

#### Added

* Added support for setting the architecture of the exectuable that is created when packaging

#### Changed

* Replaced Windows Form Designer with [PSScriptPad](https://ironmansoftware.com/psscriptpad/)
* Fixed an issue with ToolStrip items.
* Fixed an issue with deleting components

### \[5.6.1\] \(12-31-2019\)

#### Added

* Added breakpoint support to the Windows Form Designer
* Added stepping support to the Windows Form Designer
* Added support for stopping debugger to the Windows Form Designer

#### Changed

* Improved performance of IntelliSense
* Fixed a bug where the Windows Form Designer would lose code-behind changes on startup.

### \[5.6.0\] \(12-28-2019\)

#### Added

* The Windows Forms Designer can now execute PowerShell to show the form you are designing.
* The Windows Forms Designer can now package the Windows Form as a executable
* An output window was added to the Windows Forms Designer so you can see the output from your PS scripts.

### \[5.5.1\] \(12-20-2019\)

#### Changed

* Fixed an issue where the Actipro license was not installed correctly resulting in a popup.

### \[5.5.0\] \(12-20-2019\)

#### Added

* The Windows Forms Designer properties and toolbox are now in a dockable tool window.
* The Windows Forms Designer now supports moving controls with the arrow keys.

### \[5.4.6\] \(12-18-2019\)

### Added a button to open the Windows Form Designer

We’ve made it easier to open the Windows Form Designer from a PowerShell file. Just click the new Show Windows Form Designer button from your form.ps1 file.

[![](https://i2.wp.com/ironmansoftware.com/wp-content/uploads/2019/12/show-winform.png?resize=570%2C351&ssl=1)](https://i2.wp.com/ironmansoftware.com/wp-content/uploads/2019/12/show-winform.png?ssl=1)

### Fixed error message when executing commands

In certain circumstances, when you would execute PowerShell Pro Tools commands, an E\_PIPE error would be shown even though the command was completed successfully.

