---
description: Changelog for PSScriptPad
---

# PSScriptPad

## 2024.7.1 - 7/15/2024

* Fixed link to EULA
* PSScriptPad.exe is now signed

## 2024.7.0 - 7/11/2024

* PSScriptPad no longer requires a license.

## 2024.3.0 - 3/19/2024

* Fixed an issue with packaging as a service (#3184)

## 2023.9.0 - 9/7/2023

* Fixed an issue when packaging scripts with Obfuscate

## 2023.8.0 - 8/13/2023

* Editing features are now available for free

## 2023.7.1 - 7/16/2023

* Fixed a build error when packaging Windows PowerShell executables

## 2023.7.0 - 6/11/2023

* Fixed an issue in PSScriptPad that caused OpenFileDialog to fail when run within the editor
* The packager now uses the local output directory for staging rather than the temp directory to reduce AV false positives
* Reduced AV false positives for Windows PowerShell executables that do not use obfuscation
* Fixed a bug that allowed the form to be deleted in the Windows Form Designer in PSScriptPad
* Added support for bundling .NET 8.0 and 7.4 executables
* Fixed an issue where the editor could crash if an invalid license was installed

## 2023.6.0 - 6/20/2023

* Reduced AV false positives for Windows PowerShell executables that do not use obfuscation
* Added support for Lightweight PS7 executables&#x20;
* Fixed an issue with PS7 7.3.x executables not running properly
* Fixed an issue with dark mode and the WPF form designer
* Fixed a bug that allowed the form to be deleted in the Windows Form Designer in PSScriptPad

## 2023.3.0 - 3/14/2023

* Added support for bundling .NET 8.0 and 7.4 executables
* Added better logging to PSScriptPad to catch startup errors
* Added integration with PSPackager
* Added support for resetting the PSScriptPad layout

## 2023.1.1 - 1/18/2023

* Removed telemetry collection

## 2023.1.0 - 1/10/2023

* Added support for specifying any .NET or PowerShell 7 version to package
* Added command line arguments for every setting

## 2022.12.1 - 12-17-2022

* Fixed an issue where the Ironman PowerShell Host wouldn't properly set $PSScriptRoot

## 2022.12.0 - 12-13-2022

* Fixed an issue where the format on save feature could cause PSScriptPad to crash

## 2022.11.0 - 10-9-2022

* Display execution policy
* Attempt to Load PresentationFramework from multiple locations by default

## 2022.10.0 - 10-11-2022

* Added Replace Tabs with Spaces
* Validate event handler names before allowing creation of handlers
* Fixed an issue where bundled assemblies would cause unexpected output in executables
* When opening files from the context menu, the current directory is now set to the file's parent directory
* Fixed a crash that could happen when navigating history in the terminal
* Fixed an issue where bundled assemblies would cause unexpected output in executables

## 2022.9.0 - 9-13-2022

* Added support for packaging PowerShell 7.2.5 and 7.2.6 executables

## 2022.8.0 - 8-9-2022

* Fixed an issue where PSScriptPad would scroll to the top after saving
* Fixed a hang that could be caused by using the variables window while broken in the debugger.
* Added support for packaging PowerShell 7.2.4 executables

## 2022.7.0 - 7-12-2022

* Fixed an issue where license files were not correctly validated

## 2022.5.0 - 5-10-2022

* Fixed an issue where ANSI escape characters were shown in output
* Added support for packaging PS 7.2.3
* Fixed an issue where non-ASCII characters wouldn't be stored correctly after packaging

## 2022.4.1 - 4-12-2022

* Fixed an issue where Connect-ExchangeOnline would throw an exception

## 2022.4.0 - 4-12-2022

* Fixed an issue where using Clear in the terminal would produce an exception
* Fixed an issue where PowerShell 7.2 executables would not work as a service
* Fixed an issue where PowerShell 7.x executables would not have an icon
* Fixed an issue where PowerShell 7.x executables would not elevate properly

## 2022.3.0 - 3-8-2022

* Fixed an issue where a script compiled as a service would fail to run

## 2022.2.0 - 2-10-2022

* Fixed an issue where obfuscated builds wouldn't work twice
* Fixed an issue where obfuscated Windows PowerShell builds wouldn't execute correctly

## 2022.1.0 - 1-11-2022

* Added Save All button
* Fixed an issue where PowerShell 7 executables would not have file properties
* Added About dialog.

## 2021.12.1 - 12-17-2021

* Fixed an issue where packaging an executable into an output directory with an apostrophe does not work.
* Fixed an issue where PS7.1 and PS7.2 output directories would contain all unpackaged files

## 2021.12.0 - 12-14-2021

* Improved startup performance of PSScriptPad
* Fixed an issue where you couldn't view the options dialog when a Windows Form was open
* Fixed a race condition that could cause the debugger to hang was running a selection
* Added support for packaging PowerShell 7.2 and .NET 6.0 executables
* Added support for renaming the output executable
* Added an option to generate Windows Forms event handlers as functions

## 2021.11.0 - 11-9-2021

* Fixed an issue where script analyzer would highlight too many lines
* Add Scratch Pad feature
* Add support for packaging PowerShell 7.1 scripts
* Fixed an issue where you would be unable to stop long running scripts

## 2021.10.1 - 10-18-2021

* Fixed an issue where saving a file a second time would not work
* Added logging mechanism to PSScriptPad

## 2021.10.0 - 10-12-2021

* Fixed an issue where PSScriptPad would hang when saving a large file
* Fixed an issue where the default WPF XAML would not work
* PSScriptPad will now open the designer and the form

## 2021.9.0 - 9-14-2021

* Fixed an MSBuild warning that was shown when compiling on Windows
* Added support for bundling additional XAML files in executables
* Fixed an issue where using the .NET 5 SDK would cause executables to fail to build on Windows

## 5.13.3 - 7-27-2021

* Fixed an issue where DataGridView columns could not be added to the form designer

## 5.13.2 - 7-22-2021

* Fixed an issue where the packager would fail when the script name had a space in it

## 5.13.1 - 7-21-2021

* Fixed an issue where an exception could be thrown during packaging.

## 5.13.0 - 7-20-2021

* Added support for bundling resources into executables

## 5.12.3 - 7-8-2021

* Added support for packaging PowerShell 7.0.6

## 5.12.2 - 6-14-2021

* Fixed an issue where PSScriptPad would crash when pressing Ctrl+C

## 5.12.1 - 6-3-2021

* PSScriptPad layout now persists
* Add support for disabling QuickEdit during packaging
* Fixed an issue with the packager and strings with single quotes

## 5.11.5 - 6-2-2021

* Fixed a packaging issue with concatenated strings and Join-Path

## 5.11.4 - 6-1-2021

* Fixed an issue with ImageList resources would not be stored correctly

## 5.11.3 - 5-21-2021

* Added copy and paste to the Windows Form designer

## 5.11.2 - 5-20-2021

* Fixed a crash on startup in PSScriptPad
* Resolved a performance issue where analysis would run twice in PSScriptPad

## 5.11.1 - 5-19-2021

* Fixed an issue with Out-GridView

## 5.11.0 - 5-18-2021

* PSScriptAnalyzer support
* Fixed an issue where errors and warnings would not show any text when hovered

## 5.10.4 - 5-17-2021

* Fixed an issue where the terminal cursor was barely visible
* Fixed an issue where the terminal cursor would lose focus after executing a command
* Added a Grid to the default WPF window so controls are draggable by default

## 5.10.3 - 5-10-2021

* Fixed an issue with the WPF designer where it would lose focus on the current control when changing props

## 5.10.1 - 5-10-2021

* Fixed an issue where string resources would not be output in the form designer

## 5.10.0 - 4-27-2021

* Added integrated mode

## 5.9.11 - 4-23-2021

* Fixed an issue with activation caching
* Fixed an issue with packaging PowerCLI

## 5.9.10 - 4-21-2021

* Fixed an issue where packaging modules could cause an Access Denied error
* Added subscription activation caching to prevent excessive web requests

## 5.9.7 - 4-14-2021

* Fixed an issue where packaging would use the wrong PowerShell version when looking up modules causing certain modules to fail to load

## 5.9.6 - 4-7-2021

* Fixed an issue where PSScriptPad would unnecessarily allocate a console and cause a hang on some machines.

## 5.9.5 - 2-11-2021

* Fixed an issue where packaging would not work with modules that contained a C# .cs file (like MSAL.PS)

## 5.9.4 - 1-14-2021

* PSScriptPad now persists loaded WPF assembly locations so they are loaded when the application is restarted

## 5.9.3 - 1-12-2021

* Added toolbox support for the WPF designer in PSScriptPad

## 5.9.2 - 1-11-2021

* Fixed an issue where PSScriptPad could crash when opening a XAML file

## 5.9.1 - 1-10-2021

* Fixed a licensing issue with a 3rd party component

## 5.9.0 - 1-10-2021

* Added WPF Designer

## 5.8.3 - 12-26-2020

* Fixed an issue where PSScriptPad would crash when using Save As

## 5.8.2 - 12-24-2020

* Added option for Font Size
* Fixed a crash that would happen when setting a breakpoint after saving a new file
* Added support for package.psd1 config files
* Added support for opening and saving PSM1 and PSD1 files
* Fixed an issue where output from the package process would not be shown

## 5.8.1 - 12-21-2020

* Fixed an issue with the console running commands in the wrong runspace
* Fixed a display issue with the terminal

## 5.8.0 - 12-16-2020

* Settings are now stored in the registry
* Added a setting for overriding the machine's execution policy
* Fixed an issue where errors would be thrown when attempting to view variables in Windows PowerShell

## 5.7.7 - 12-2-2020

* Added support for PowerShell Pro Tools subscriptions

## 5.7.6 - 11-21-2020

* Fixed an issue where the license link would go to a 404 page.

## 5.7.5 - 11-4-2020

* Fixed an issue with packaging the NTFSSecurity module

## 5.7.4 - 9-29-2020

**Changed**

* Fixed an issue where variables would not be shown during debugging.

## 5.7.2 – 9-13-2020

**Changed**

* Default install of trial key

## 5.7.1 – 7-22-2020

**Changed**

* Fixed an issue where breakpoints would not be hit
* Fixed an issue where a document would not be activated when debugging.

## 5.7.0 – 7-22-2020

**Added**

* Added support for light and dark themes

## 5.6.7 – 7-16-2020

**Changed**

* Fixed an issue with PSScriptPad where the variables window wouldn’t expand variables correctly

## 5.6.6 – 7-15-2020

**Changed**

Fixed an issue where internal logging would be shown in the console.

## 5.6.4 – 7-12-2020

**Changed**

Fixed an issue where ListView, TreeView and ContextMenu child items would not work in PSScriptPad\
Fixed an issue where packaging would fail if a script ended in a comment\
Fixed an issue where packaging would fail if a script was too large\
Fixed an issue where the opacity setting wouldn’t work on form controls on certain systems.

## 5.6.3 – 6-19-2020

**Changed**

* Fixed an issue with the form designer that wouldn’t be marked dirty when properties were edited
* Fixed an issue with the form designer where it wouldn’t save StatusStrip items
* Fixed an issue with the form designer where it wouldn’t change the main PS1’s form name if it was changed in the designer

## 5.6.2 – 5-6-2020

**Changed**

* Fixed an issue that was causing hangs when running WinForm scripts.

## 5.6.1 – 4-6-2020

**Changed**

* Fixed an issue where putting an apostrophe in a label would cause the Form Designer to fail to load
* Fixed an issue where copy and pasting text into PSScriptPad would cause it to crash

## 5.6.0 – 3-27-2020

**Added**

– Added PSReadline Support

## 5.5.1 – 3-22-2020

### Added

* Console Window

### Modified

* Fixed an issue where WinForms would be hidden when running them from PSScriptPad.

## 5.5.0 – 3-18-2020

### Added

* PowerShell 7 Support

## 5.4.4 – 2-10-2020

### Changed

– Fixed an issue where a failed packaging build would not show the error message in the output

## 5.4.2 – 1-31-2020

### Added

– Added an option to add a context menu item for opening PS1 files with PSScriptPad\
– Added support for Comment (Ctrl+K,Ctrl+C) and Uncomment (Ctrl+K,Ctrl+U) keyboard shortcuts\
– Added support for reloading files updated outside of PSScriptPad

### Changed

– Fixed a crash that could happen on startup due to a threading issue

## 5.4.1 – 1-28-2020

### Changed

– Fixed issue where packaged applications wouldn’t work with arguments with spaces

## 5.3.2 – 1-21-2020

### Added

* Splash screen
* Added restart\restart as admin buttons
* Options dialog
* Added ability to optimize startup speed

### Changed

* Fixed an issue where setting a breakpoint would cause syntax highlighting to disappear
* Tool windows are auto-docked when opening a Windows Form

## 5.3.1 – 1-21-2020

### Changed

* PowerShellProTools module is now signed
* Fixed an issue with PSScriptPad that was preventing typing while IntelliSense was running in the terminal

## 5.3.0 – 1-18-2020

### Added

Support for generating resources such as images and icons for WinForms.

### Changed

Fixed issue with packaging resources used for WinForms.

## 5.2.6 – 1-15-2020

### Changed

* Improved licensing error messages and improved performance of license checking.

## 5.2.5 – 1-14-2020

### Changed

* Fixed an issue where the debugger would not start the second time

## 5.2.4 – 1-13-2020

### Added

* Added support for Clear-Host

### Changed

* Fixed an issue where the debugging status indicator would not advance correctly
* Fixed an issue where the terminal would be disabled if broken in the debugger
* Fixed an issue where output to the terminal would not appear on a new line
* Fixed an issue where you would need to invoke debugging commands twice (Step Over, Step Into, Continue, Stop)

## 5.2.3 – 1-12-2020

### Changed

* Fixed an issue where packaging would throw an invalid format exception
* Fixed an issue with package architecture

## 5.2.2 – 1-10-2020

### Added

* Added a What’s New link that points to the changelog

### Changed

* Fixed issue with strings in the variables tool window
* Fixed issue with terminal attempting to run commands while the runspace was busy
* Terminal now executes on a background thread so the UI doesn’t lock up
* Fixed an issue where the entire script would be collapsible.
* Fixed issue that would prevent the license from being installed through the UI
