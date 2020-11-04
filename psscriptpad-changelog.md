---
description: Changelog for PSScriptPad
---

# PSScriptPad

### 5.7.5 - 11-4-2020

* Fixed an issue with packaging the NTFSSecurity module

### 5.7.4 - 9-29-2020

**Changed**

* Fixed an issue where variables would not be shown during debugging.

### 5.7.2 – 9-13-2020

**Changed**

* Default install of trial key

### 5.7.1 – 7-22-2020

**Changed**

* Fixed an issue where breakpoints would not be hit
* Fixed an issue where a document would not be activated when debugging.

### 5.7.0 – 7-22-2020

**Added**

* Added support for light and dark themes

### 5.6.7 – 7-16-2020

**Changed**

* Fixed an issue with PSScriptPad where the variables window wouldn’t expand variables correctly

### 5.6.6 – 7-15-2020

**Changed**

Fixed an issue where internal logging would be shown in the console.

### 5.6.4 – 7-12-2020

**Changed**

Fixed an issue where ListView, TreeView and ContextMenu child items would not work in PSScriptPad  
Fixed an issue where packaging would fail if a script ended in a comment  
Fixed an issue where packaging would fail if a script was too large  
Fixed an issue where the opacity setting wouldn’t work on form controls on certain systems.

### 5.6.3 – 6-19-2020

**Changed**

* Fixed an issue with the form designer that wouldn’t be marked dirty when properties were edited
* Fixed an issue with the form designer where it wouldn’t save StatusStrip items
* Fixed an issue with the form designer where it wouldn’t change the main PS1’s form name if it was changed in the designer

### 5.6.2 – 5-6-2020

**Changed**

* Fixed an issue that was causing hangs when running WinForm scripts.

### 5.6.1 – 4-6-2020

**Changed**

* Fixed an issue where putting an apostrophe in a label would cause the Form Designer to fail to load
* Fixed an issue where copy and pasting text into PSScriptPad would cause it to crash

### 5.6.0 – 3-27-2020

**Added**

– Added PSReadline Support

### 5.5.1 – 3-22-2020

#### Added

* Console Window

#### Modified

* Fixed an issue where WinForms would be hidden when running them from PSScriptPad.

### 5.5.0 – 3-18-2020

#### Added

* PowerShell 7 Support

### 5.4.4 – 2-10-2020

#### Changed

– Fixed an issue where a failed packaging build would not show the error message in the output

### 5.4.2 – 1-31-2020

#### Added

– Added an option to add a context menu item for opening PS1 files with PSScriptPad  
– Added support for Comment \(Ctrl+K,Ctrl+C\) and Uncomment \(Ctrl+K,Ctrl+U\) keyboard shortcuts  
– Added support for reloading files updated outside of PSScriptPad

#### Changed

– Fixed a crash that could happen on startup due to a threading issue

### 5.4.1 – 1-28-2020

#### Changed

– Fixed issue where packaged applications wouldn’t work with arguments with spaces

### 5.3.2 – 1-21-2020

#### Added

* Splash screen
* Added restart\restart as admin buttons
* Options dialog
* Added ability to optimize startup speed

#### Changed

* Fixed an issue where setting a breakpoint would cause syntax highlighting to disappear
* Tool windows are auto-docked when opening a Windows Form

### 5.3.1 – 1-21-2020

#### Changed

* PowerShellProTools module is now signed
* Fixed an issue with PSScriptPad that was preventing typing while IntelliSense was running in the terminal

### 5.3.0 – 1-18-2020

#### Added

Support for generating resources such as images and icons for WinForms.

#### Changed

Fixed issue with packaging resources used for WinForms.

### 5.2.6 – 1-15-2020

#### Changed

* Improved licensing error messages and improved performance of license checking.

### 5.2.5 – 1-14-2020

#### Changed

* Fixed an issue where the debugger would not start the second time

### 5.2.4 – 1-13-2020

#### Added

* Added support for Clear-Host

#### Changed

* Fixed an issue where the debugging status indicator would not advance correctly
* Fixed an issue where the terminal would be disabled if broken in the debugger
* Fixed an issue where output to the terminal would not appear on a new line
* Fixed an issue where you would need to invoke debugging commands twice \(Step Over, Step Into, Continue, Stop\)

### 5.2.3 – 1-12-2020

#### Changed

* Fixed an issue where packaging would throw an invalid format exception
* Fixed an issue with package architecture

### 5.2.2 – 1-10-2020

#### Added

* Added a What’s New link that points to the changelog

#### Changed

* Fixed issue with strings in the variables tool window
* Fixed issue with terminal attempting to run commands while the runspace was busy
* Terminal now executes on a background thread so the UI doesn’t lock up
* Fixed an issue where the entire script would be collapsible.
* Fixed issue that would prevent the license from being installed through the UI

