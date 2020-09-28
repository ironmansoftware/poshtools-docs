---
description: Changelog for PowerShell Tools for Visual Studio
---

# PowerShell Tools for Visual Studio

{% hint style="info" %}
This page contains the changelog for both PowerShell Tools for Visual Studio and [PowerShell Pro Tools for Visual Studio](https://ironmansoftware.com/powershell-pro-tools-for-visual-studio/).
{% endhint %}

### 5.6.4 - 9-28-2020

**Changed**

* Fixed an issue where the error list line number would be off by one
* Fixed an issue with bundling the ActiveDirectory module in PowerShell 7 standalone executables

### 5.6.3 - 9-24-2020

**Changed**

* Fixed an issue where compiling a PowerShell 7 executable that included WinForms wouldn't work if Hide Console Window was unchecked. 

### 5.6.2 - 9-22-2020

**Changed**

* Fixed an issue where parse errors would not be highlighed
* Fixed an issue where clicking a parse or analysis error in the error list would throw an exception
* Fixed an issue with the NumericDropDown Windows Form component would not be generated correctly. 

### 5.6.1 - 9-17-2020

**Changed**

* Fixed an issue with packaging Windows Forms applications with PS7

### 5.6.0 - 9-16-2020

**Added**

* Added support for packaging the 7.0.2 and 7.0.3 PowerShell SDK

### 5.5.7 - 9-13-2020

**Changed**

* Default install of PowerShell Pro Tools trial license

### 5.5.6 – 9-01-2020

**Changed**

* Fixed an issue where script analyzer support could cause a hang when changing languages or starting Visual Studio

### 5.5.5 – 8-05-2020

**Changed**

Reverting changes in version 5.5.4 that resulted in commands not executing correctly

Fixed an issue with PSScriptAnaylzer support

### 5.5.4 – 7-31-2020

**Changed**

Fixed an issue where parser errors would be shown for PS7’s new features

### 5.5.3 – 7-14-2020

**Changed**

Fixed an issue where the locals window wouldn’t display variables

### 5.5.2 – 7-12-2020

**Changed**

Fixed an issue where ListView, TreeView and ContextMenu child items would not work in PSScriptPad  
Fixed an issue where packaging would fail if a script ended in a comment  
Fixed an issue where packaging would fail if a script was too large  
Fixed an issue where the opacity setting wouldn’t work on form controls on certain systems.  
Fixed an issue where script analysis would highlight too much of the script when there was an issue  
Fixed an issue where script analysis quickfix items would replace too much of the script

### 5.5.1 – 6-2-2020

**Changed**

* Fixed an issue where packaging would fail for projects created with 5.4.9 or older

### 5.5.0 – 5-26-2020

**Added**

* Added support for packaging PowerShell 7 executables
* Added experimental support for packaging Linux and OSX executables

**Changed**

* Fixed an issue that could cause a crash if PSScriptAnalyzer was enabled
* Fixed an issue where QuickFix items could cause a crash when being executed

### 5.4.9 – 5-18-2020

**Changed**

* Fixed a crash that could happen when PSScriptAnalyzer was enabled
* Fixed an issue that would cause breakpoints to not be hit when lines were indented

### 5.4.8 – 5-6-2020

**Changed**

* Fixed an issue where removing a breakpoint would not clear the breakpoint in PowerShell
* Fixed an issue where output could be written out of order

### 5.4.7 – 5-6-2020

**Changed**

* Fixed an issue that was causing hangs when running WinForm scripts.

### 5.4.6 – 2020-4-30

**Changed**

* Fixed an issue where stopping the debugger could prevent it from starting again
* Fixed an issue where using statements in a script would prevent it from packaging correctly
* Add logging to the packaging system to better diagnose issues.
* 
### 5.4.5 – 2020-4-27

**Changed**

* Fixed an issue with variables not expanding properly in the Locals and Watch windows.
* Fixed an issue with an exception being shown during startup due to the Analysis Service not being ready
* Fixed an issue with the output pane no longer showing script output
* Fixed an issue where terminating errors would not be shown

### 5.4.4 – 2020-4-19

**Changed**

* Removed the experimental console for now as it was causing unexpected issues for some users.

### 5.4.2 – 2020-4-16

**Changed**

* Fixed an issue where the extension would allocate a console window on startup

**Known Issues**

* The console window may be allocated outside of Visual Studio and the PowerShell Console \(Experimental\) window will cause VS to become unresponsive.

### 5.4.1 – 2020-4-13

**Changed**

* Fixed an issue with installation into Visual Studio 2017

### 5.4.0 – 2020-4-12

**Added**

* Added a new PowerShell Console window. Click View-&gt;Other Windows-&gt;PowerShell Console to open it.

**Changed**

* Removed dependency on gRPC to reduce hangs when using PoshTools
* Improved performance of the Attach to Process dialog when PoshTools is installed
* Fixed icons for PowerShell-based nodes in the solution explorer

### 5.3.6 – 2020-3-27

**Added**

– Added a $Service object to OnStart\OnStop for packaged services to access the ServiceBase for the service  
– Added $ProcessArgs and $ServiceArgs variables to the runspace for packaged services

**Changed**

– Fixed an issue where Execute Selection would not show up in folder view  
– Fixed an issue where $PSScriptRoot would not work for packaged services  
– Updated signing certificate

### 5.3.5 – 2020-2-28

**Changed**– Fixed an issue where the solution directory would not be set when opening a solution or switching PowerShell versions– Fixed issue where the $dte variable may not be present– Fixed an issue where the service process would not log

### 5.3.4 – 2020-2-10

#### Added

– Added a Script property to the debug settings to allow for running a specific script rather than the currently open script

#### Changed

– Fixed an issue where a failed packaging build would not show the error message in the output

### 5.3.3 – 2020-2-4

#### Added

* Added a PowerShell Windows Forms Project template

#### Changed

* Fixed an issue when setting the platform for a packaged script
* Fixed an issue when setting the “PackagePowerShell” setting for a packaged script
* Fixed a syntax error with the Windows Forms item template

### 5.3.2 – 2020-1-28

#### Changed

* Fixed issue with resource generation in Visual Studio Windows Forms Designer
* Fixed issue where packaged applications wouldn’t work with arguments with spaces

### 5.3.1 – 2020-1-22

No longer requires a [trial key](https://ironmansoftware.com/simplifying-product-trial-licensing/)

### 5.2.5 – 2020-1-21

#### Fixed an issue with PowerShell Pro Tools initializing

Depending on how the PowerShell Pro Tools extension was loaded an error would be shown and it would fail to loaded.

### 5.2.4 – 2020-1-18

#### Fixed an issue with bundling resources

Resources, such as images and icons, would not be bundled correctly when bundling a WinForm control.

### 5.2.3 – 2020-1-16

#### Fixed an issue with license checking for the WinForm designer

If you opened the WinForm designer before installing your license, then installed a license and then opened the WinForm designer, you would need to restart Visual Studio for the license to take effect.

### 5.2.2 – 2020-1-15

#### Republished 5.2.1 as 5.2.2

An issue with the marketplace was causing a failure when upgrading to 5.2.1. Republished as 5.2.2 and it seems to have resolved it.

### 5.2.1 – 2020-1-15

#### Fixed an issue with license activation

License activation could run more than once causing the product to think that it was unlicensed.

### 5.2.0 – 2020-1-14

#### Added Platform Settings to Packaging

You can now specify the platform \(x64\x86\) when packaging executables.

### 5.1.4 – 2019-11-21

#### Fixed Crash During Start up or Solution Load

There was a race condition between the PowerShell host starting and the gRPC client being available to set the location of the REPL window. This would cause a crash when VS was starting and loading a PS solution at the same time.

#### Fixed Crash when selecting PS Script Analyzer Rules

When selecting PS Script Analyzer rules, there could be a condition where a directory needed to store the settings would not exist. This directory is now created before attempting to save the settings.

#### Added STA Support for Windows PowerShell

In the General options page, you can now select STA mode for Windows PowerShell. This primarily affects Windows Forms controls, like the web browser control, that rely on COM.

### 5.1.3 – 2019-11-19

#### Hang when running command-line tools

Command-line tools that used the error stream \(like git.exe\) would cause a hang in the PowerShell debugger.

### 5.1.2 – 2019-11-18

#### Visual Studio: Fixed Aggressive Extension Loading

The PoshTools extension was loading aggressively. It would load even when no PowerShell solution or interactive window was open.

#### Visual Studio: Fixed exception in script analyzer

When Visual Studio was loading, the script analyzer would attempt to analyze “null” file resulting in an error.

#### Visual Studio: Added Convert to PowerShell command

The Paste As command was replaced with Convert to PowerShell.

### 5.1.1 – 2019-11-15

#### Visual Studio: Visual Studio would hang when using PowerShell v3\v4

When the PowerShell extension would initialize and PowerShell v3 or v4 was being used, the extension would cause the IDE to hang.

#### Visual Studio: Debugging would not work in Visual Studio 2017

The error “Attaching the PowerShell Debug Engine debugger to Process unknown process” would be shown when attempting to debug.

#### Visual Studio: Breakpoint would not be set in Visual  Studio 2017

The debugger would not break on a breakpoint set in Visual Studio 2017.

### 5.1.0 – 2019-11-11

#### Visual Studio: Solution Wide Analysis

[PowerShell Pro Tools](https://ironmansoftware.com/powershell-pro-tools/) now uses [PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer) to analyze all the scripts within your solution in the background. You will still see tags on the active file, but the error list will also report any issues with any PSM1 or PS1 files in your solution.

![](https://i2.wp.com/ironmansoftware.com/wp-content/uploads/2019/11/solution-wide-analysis.png?resize=961%2C626&ssl=1)

#### Visual Studio: PSScriptAnalyzer Settings

You can now modify PSScriptAnalyzer settings directly in the PowerShell Tools Options. Go to the Analysis page to turn on Analysis, Solution Wide Analysis, enable specific levels or even turn off specific rules.

![](https://i2.wp.com/ironmansoftware.com/wp-content/uploads/2019/11/analysis-options.png?resize=1005%2C663&ssl=1)

#### Visual Studio Code: Fixed PowerShell Host Initialization

The PowerShell Pro Tools host could fail to initialize so startup operations would not be performed putting the extension in an unknown state. The extension has been fixed to load the host consistenlty.

#### Visual Studio Code: Fixed PowerShell Host Crash Reinitialization

If the Visual Code PowerShell Host would crash, PowerShell Pro Tools would not reconnect to the PowerShell process. This would prevent it from working.

