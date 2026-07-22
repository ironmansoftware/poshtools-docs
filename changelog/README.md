---
description: Changelog for PowerShell Tools and PowerShell Pro Tools.
---

# 2024.7.1

Released: 2024-07-15

## PSScriptPad

* Fixed link to EULA
* PSScriptPad.exe is now signed

# 2024.7.0

Released: 2024-07-11

## PSScriptPad


# 2024.3.1

Released: 2024-03-29

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where VS Code would report command not found when PowerShell Pro Tools was starting.

# 2024.3.0

Released: 2024-03-19

## PowerShell Tools for Visual Studio

* Fixed an issue with packaging as a service (#3184)

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue with packaging as a service (#3184)

## PowerShell Packager

* Fixed an issue with packaging as a service (#3184)

## PSScriptPad

* Fixed an issue with packaging as a service (#3184)

## PowerShell Pro Tools Module

* Fixed an issue with packaging as a service (#3184)

# 2024.2.1

Released: 2024-03-18

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where PoshTools wouldn't connect when persistent terminals were enabled

# 2024.2.0

Released: 2024-02-20

## PowerShell Pro Tools for Visual Studio Code

* Added a Retry option when PowerShell Pro Tools fails to connect
* Added more logging to connect failures

# 2024.1.0

Released: 2024-01-29

## PowerShell Tools for Visual Studio

* Fixed an issue with project system icons
* Added a search bar to the PSScriptAnalyzer rules
* Fixed an issue with the High DPI Setting for packaged executables.

# 2023.12.2

Released: 2024-01-17

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where Generate Windows Form would not run properly.

# 2023.12.1

Released: 2024-01-09

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue that could result in extension activation crashing VS Code

# 2024.1.0

Released: 2024-01-04

## PowerShell Packager

* Added support for signing executables
* Added diagnostic logging
* Fixed an issue with the output pane not scrolling properly.

# 2023.12.0

Released: 2023-12-10

## PowerShell Pro Tools for Visual Studio Code

* Added support for all supported PowerShell platforms.
* Added method overloads hover.
* Added support for bundling PowerShell 7.4 and .NET 8.0 executables.

# 2023.9.0

Released: 2023-09-07

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue when packaging scripts with Obfuscate

## PSScriptPad

* Fixed an issue when packaging scripts with Obfuscate

## PowerShell Pro Tools Module

* Fixed an issue when packaging scripts with Obfuscate

# 2023.8.0

Released: 2023-08-13

## PowerShell Tools for Visual Studio

* Fixed an issue with the Extract as Function refactoring
* Removed support for WPF in VS 2022

## PowerShell Pro Tools for Visual Studio Code

* Updated version of PSScriptPad

## PSScriptPad

* Editing features are now available for free

# 2023.7.1

Released: 2023-07-16

## PowerShell Tools for Visual Studio

* Fixed a build error when packaging Windows PowerShell executables

## PowerShell Pro Tools for Visual Studio Code

* Fixed a build error when packaging Windows PowerShell executables

## PSScriptPad

* Fixed a build error when packaging Windows PowerShell executables

## PowerShell Pro Tools Module

* Fixed a build error when packaging Windows PowerShell executables

# 2023.7.0

Released: 2023-07-11

## PowerShell Tools for Visual Studio

* Added support for Visual Studio 2022 Windows ARM64

# 2023.6.0

Released: 2023-06-20

## PowerShell Tools for Visual Studio

* Added a close button to the new version notification bar.
* Fixed an issue with PS7 7.3.x executables not running properly

## PowerShell Pro Tools for Visual Studio Code

* Updated version of PSScriptPad
* Added support for Lightweight PS7 executables
* Fixed an issue with PS7 7.3.x executables not running properly

## PowerShell Packager

* Added installation directory selector during upgrade

## PSScriptPad

* Reduced AV false positives for Windows PowerShell executables that do not use obfuscation
* Added support for Lightweight PS7 executables
* Fixed an issue with PS7 7.3.x executables not running properly
* Fixed an issue with dark mode and the WPF form designer
* Fixed a bug that allowed the form to be deleted in the Windows Form Designer in PSScriptPad

# 2023.7.0

Released: 2023-06-11

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue in PSScriptPad that caused OpenFileDialog to fail when run within the editor
* The packager now uses the local output directory for staging rather than the temp directory to reduce AV false positives
* Reduced AV false positives for Windows PowerShell executables that do not use obfuscation
* Fixed a bug that allowed the form to be deleted in the Windows Form Designer in PSScriptPad
* Added support for bundling .NET 8.0 and 7.4 executables

## PSScriptPad

* Fixed an issue in PSScriptPad that caused OpenFileDialog to fail when run within the editor
* The packager now uses the local output directory for staging rather than the temp directory to reduce AV false positives
* Reduced AV false positives for Windows PowerShell executables that do not use obfuscation
* Fixed a bug that allowed the form to be deleted in the Windows Form Designer in PSScriptPad
* Added support for bundling .NET 8.0 and 7.4 executables

## PowerShell Pro Tools Module

* Fixed an issue in PSScriptPad that caused OpenFileDialog to fail when run within the editor
* The packager now uses the local output directory for staging rather than the temp directory to reduce AV false positives
* Reduced AV false positives for Windows PowerShell executables that do not use obfuscation
* Fixed a bug that allowed the form to be deleted in the Windows Form Designer in PSScriptPad
* Added support for bundling .NET 8.0 and 7.4 executables

# 2023.3.0

Released: 2023-03-14

## PowerShell Pro Tools for Visual Studio Code

* Updated version of PSScriptPad

## PowerShell Packager

* Added support for loading package.psd1 files

## PSScriptPad

* Added support for bundling .NET 8.0 and 7.4 executables
* Added better logging to PSScriptPad to catch startup errors
* Added integration with PSPackager
* Added support for resetting the PSScriptPad layout

## PowerShell Pro Tools Module

* Added better logging to PSScriptPad to catch startup errors
* Fixed an issue where FileDescription would not be set properly on executables
* Updated version of PSScriptPad

# 2023.2.1

Released: 2023-03-01

## PowerShell Tools for Visual Studio

* Fixed an issue with Go To Definition and classes
* Fixed an issue where script analyzer would not highlight scripts properly
* Fixed an issue with the File Description property for packaged executables

# 2023.2.0

Released: 2023-02-27

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where specifying an icon with the IronmanPowerShellHost would cause the executable to fail to run.

## PowerShell Packager

* Fixed an issue where specifying an icon with the IronmanPowerShellHost would cause the executable to fail to run.

## PowerShell Pro Tools Module

* Fixed an issue where specifying an icon with the IronmanPowerShellHost would cause the executable to fail to run.

# 2023.2.0

Released: 2023-02-14

## PowerShell Tools for Visual Studio

* Added support for .editorconfig files
* Improved performance of analysis of large projects
* Fixed issues with Go To Definition on large projects
* Fixed an issue where the Locals window would hang when expanding large arrays or objects

# 2023.1.1

Released: 2023-01-18

## PSScriptPad

* Removed telemetry collection

# 2023.1.0

Released: 2023-01-10

## PowerShell Pro Tools for Visual Studio Code

* Added support for specifying any .NET or PowerShell 7 version to package
* Fixed an issue where the IronmanPowerShellHost would truncate the first 3 characters
* Fixed an issue where the IronmanPowerShellHost would not accept arguments

## PowerShell Packager

* Added support for specifying any .NET or PowerShell 7 version to package
* Fixed an issue where the IronmanPowerShellHost would not accept arguments
* Fixed an issue where the IronmanPowerShellHost would truncate the first 3 characters

## PSScriptPad

* Added support for specifying any .NET or PowerShell 7 version to package
* Added command line arguments for every setting

## PowerShell Pro Tools Module

* Added support for specifying any .NET or PowerShell 7 version to package
* Merge-Script now outputs build progress by default
* Fixed an issue where the IronmanPowerShellHost would truncate the first 3 characters
* Fixed an issue where the IronmanPowerShellHost would not accept arguments

# 2022.12.2

Released: 2023-01-07

## PowerShell Pro Tools Module

* Fixed an issue where the IronmanPowerShellWinFormsHost wouldn't run anything

# 2022.12.2

Released: 2023-01-05

## PowerShell Packager

* Fixed an issue where the IronmanPowerShellWinFormsHost wouldn't run anything

# 2022.12.1

Released: 2023-01-04

## PowerShell Tools for Visual Studio

* Fixed an issue where Go To Definition wouldn't work for parameters or members within a class using the `$this` variable.

# 2022.12.2

Released: 2022-12-17

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where the Ironman PowerShell Host wouldn't properly set $PSScriptRoot

# 2022.12.1

Released: 2022-12-17

## PowerShell Packager

* Fixed an issue where the Ironman PowerShell Host wouldn't properly set $PSScriptRoot

## PSScriptPad

* Fixed an issue where the Ironman PowerShell Host wouldn't properly set $PSScriptRoot

## PowerShell Pro Tools Module

* Fixed an issue where the Ironman PowerShell Host wouldn't properly set $PSScriptRoot

# 2022.12.1

Released: 2022-12-16

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where the form designer would not open

# 2022.12.0

Released: 2022-12-13

## PowerShell Tools for Visual Studio

* Add supported for navigating to class definitions via Go To Definition
* Fixed an issue where packaging scripts with Unicode characters
* Improved auto-install of PSScriptAnalyzer
* Fixed an issue where Go To Definition was displayed twice in the editor context menu
* Fixed an issue where refreshing the variables window would cause VS to hang

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where the packager wouldn't correctly pacakge scripts with Unicode characters

## PSScriptPad

* Fixed an issue where the format on save feature could cause PSScriptPad to crash

## PowerShell Pro Tools Module

* Removed features that are now available for free
* Add support for icons in the Ironman Software Host Process

# 2022.11.3

Released: 2022-11-29

## PowerShell Packager

* Added support for packaging icons

# 2022.11.2

Released: 2022-11-28

## PowerShell Packager

* Fixed an issue where the Require Elevation parameter would not work
* Fixed an issue where modules would not be loaded correctly in packaged executables.
* Fixed an issue where invalid File Versions would cause the packager to fail

# 2022.11.1

Released: 2022-11-28

## PowerShell Tools for Visual Studio

* Fixed an issue where the Variables window would hang VS when debugging
* Fixed an issue where the Variables window would not refresh properly while debugging

## PowerShell Packager

* Fixed an issue where the packager would start on Windows startup

# 2202.11.0

Released: 2022-11-16

## PowerShell Packager

* Initial release

# 2022.11.2

Released: 2022-11-14

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where unsigned DLLs were not loaded successfully when packaging executables

# 2022.11.1

Released: 2022-11-14

## PowerShell Pro Tools Module

* Fixed an issue where unsigned DLLs were not loaded successfully when packaging executables

# 2022.11.1

Released: 2022-11-11

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where PSScriptPad failed to launch from VS Code.

# 2022.11.0

Released: 2022-11-09

## PowerShell Tools for Visual Studio

* Changed logging framework
* Removed the Ctrl+C shortcut to clear the screen in the PowerShell Interactive Window

## PowerShell Pro Tools for Visual Studio Code

* Added Ironman Software host for packaging

## PowerShell Pro Tools Module

* Added Ironman Software Host Process

# 2022.10.1

Released: 2022-10-13

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where the variable explorer would be empty

# 2022.10.0

Released: 2022-10-11

## PowerShell Tools for Visual Studio

* Fixed an issue where button1 was defined in forms by default
* Added EnableVisualStyles to the default form template
* Fixed a crash that could happen when using the function drop down in the code editor
* Fixed an issue where PSScriptAnalyzer would fail to install
* Enabled line numbers by default
* Fixed an issue where event handlers could be created with invalid characters
* Diagnostics is now always enabled
* Fixed an issue where bundled assemblies would cause unexpected output in executables

## PowerShell Pro Tools for Visual Studio Code

* Added PowerShell Performance output
* Fixed an issue where bundled assemblies would cause unexpected output in executables

## PSScriptPad

* Added Replace Tabs with Spaces
* Validate event handler names before allowing creation of handlers
* Fixed an issue where bundled assemblies would cause unexpected output in executables
* When opening files from the context menu, the current directory is now set to the file's parent directory
* Fixed a crash that could happen when navigating history in the terminal
* Fixed an issue where bundled assemblies would cause unexpected output in executables

## PowerShell Pro Tools Module

* Fixed an issue where you couldn't create 2 shortcuts to the same file with New-Installer
* Fixed an issue where bundled assemblies would cause unexpected output in executables

# 2022.11.0

Released: 2022-10-09

## PSScriptPad

* Display execution policy
* Attempt to Load PresentationFramework from multiple locations by default

# 2022.9.0

Released: 2022-09-13

## PowerShell Tools for Visual Studio

* Added support for packaging PowerShell 7.2.5 and 7.2.6 executables
* Added support for switch parameters with Convert To Splat

## PowerShell Pro Tools for Visual Studio Code

* Added support for packaging PowerShell 7.2.5 and 7.2.6 executables
* Added support for switch parameters with Convert To Splat

## PSScriptPad

* Added support for packaging PowerShell 7.2.5 and 7.2.6 executables

## PowerShell Pro Tools Module

* Added support for packaging PowerShell 7.2.5 and 7.2.6 executables

# 2022.8.0

Released: 2022-08-09

## PowerShell Tools for Visual Studio

* Added support for packaging PowerShell 7.2.4 executables

## PowerShell Pro Tools for Visual Studio Code

* Added support for packaging PowerShell 7.2.4 executables

## PSScriptPad

* Fixed an issue where PSScriptPad would scroll to the top after saving
* Fixed a hang that could be caused by using the variables window while broken in the debugger.
* Added support for packaging PowerShell 7.2.4 executables

## PowerShell Pro Tools Module

* Added support for packaging PowerShell 7.2.4 executables

# 2022.7.1

Released: 2022-08-02

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where the extension would fail to activate.

# 2022.7.0

Released: 2022-07-12

## PowerShell Tools for Visual Studio


## PowerShell Pro Tools for Visual Studio Code


## PSScriptPad


## PowerShell Pro Tools Module


# 2022.6.0

Released: 2022-06-14

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where the icon was incorrect for PowerShell Pro Tools

# 2022.5.2

Released: 2022-05-31

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where the form designer would not be shown even when the setting was enabled.

# 2022.5.0

Released: 2022-05-10

## PowerShell Tools for Visual Studio

* Fixed an issue where syntax errors would be shown as warnings
* Added support for packaging PS 7.2.3
* Fixed an issue where non-ASCII characters wouldn't be stored correctly after packaging

## PowerShell Pro Tools for Visual Studio Code

* Added settings to hide the buttons in the toolbar
* Added support for packaging PS 7.2.3
* Fixed an issue where non-ASCII characters wouldn't be stored correctly after packaging

## PSScriptPad

* Fixed an issue where ANSI escape characters were shown in output
* Added support for packaging PS 7.2.3
* Fixed an issue where non-ASCII characters wouldn't be stored correctly after packaging

## PowerShell Pro Tools Module

* Fixed an issue where the link to the docs from Show-PSEditor would end in a 404
* Fixed an issue where ANSI escape characters were shown in Show-PSEditor output
* Added support for packaging PS 7.2.3
* Fixed an issue where non-ASCII characters wouldn't be stored correctly after packaging

# 2022.4.3

Released: 2022-04-15

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where the welcome page would be blank
* Fixed an issue where an exception would be thrown when moving arguments
* Fixed a typo in the introduce using namespace refactoring
* Fixed an issue where Generate Proxy Function would add an additional blank line on Windows
* Fixed an issue where Rename Symbol would not work properly
* Fixed an issue where Use parameter splatting wouldn't work with switch parameters
* Fixed an issue where Use parameter splatting wouldn't work for commands line a pipeline
* Fixed an issue where providers would not load correctly

# 2022.4.1

Released: 2022-04-12

## PSScriptPad

* Fixed an issue where Connect-ExchangeOnline would throw an exception

# 2022.4.0

Released: 2022-04-12

## PowerShell Tools for Visual Studio

* Removed code conversion features
* Fixed an issue where Read-Host would not work in VS2022
* Fixed an issue where PowerShell 7.2 executables would not work as a service
* Fixed an issue where PowerShell 7.x executables would not have an icon
* Fixed an issue where PowerShell 7.x executables would not elevate properly

## PowerShell Pro Tools for Visual Studio Code

* Removed code conversion features
* Added support for MacOS ARM64
* Fixed an issue where the extension would not load properly on MacOS or Linux
* Fixed an issue where PowerShell 7.2 executables would not work as a service
* Fixed an issue where PowerShell 7.x executables would not have an icon
* Fixed an issue where PowerShell 7.x executables would not elevate properly

## PSScriptPad

* Fixed an issue where using Clear in the terminal would produce an exception
* Fixed an issue where PowerShell 7.2 executables would not work as a service
* Fixed an issue where PowerShell 7.x executables would not have an icon
* Fixed an issue where PowerShell 7.x executables would not elevate properly

## PowerShell Pro Tools Module

* Added support for shortcuts to directories.
* Removed code conversion features
* Added Show-PSEditor
* Added Show-TUIDesigner
* Fixed an issue where PowerShell 7.2 executables would not work as a service
* Fixed an issue where PowerShell 7.x executables would not have an icon
* Fixed an issue where PowerShell 7.x executables would not elevate properly

# 2022.3.0

Released: 2022-03-08

## PowerShell Tools for Visual Studio

* Fixed an issue where a script compiled as a service would fail to run
* Fixed an issue where running the code formatter would remove breakpoints

## PowerShell Pro Tools for Visual Studio Code

* Added Extract Variable refactoring
* Fixed an issue where a script compiled as a service would fail to run

## PSScriptPad

* Fixed an issue where a script compiled as a service would fail to run

## PowerShell Pro Tools Module

* Fixed an issue where a script compiled as a service would fail to run
* Fixed an issue where compiling on Linux would fail

# 2022.2.1

Released: 2022-02-10

## PowerShell Tools for Visual Studio

* Fixed an issue where obfuscated builds wouldn't work twice
* Fixed an issue where obfuscated Windows PowerShell builds wouldn't execute correctly

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where obfuscated builds wouldn't work twice
* Fixed an issue where obfuscated Windows PowerShell builds wouldn't execute correctly

## PowerShell Pro Tools Module

* Fixed an issue where obfuscated builds wouldn't work twice
* Fixed an issue where obfuscated Windows PowerShell builds wouldn't execute correctly

# 2022.2.0

Released: 2022-02-10

## PSScriptPad

* Fixed an issue where obfuscated builds wouldn't work twice
* Fixed an issue where obfuscated Windows PowerShell builds wouldn't execute correctly

# 2022.2.0

Released: 2022-02-08

## PowerShell Tools for Visual Studio

* Fixed an issue where File Description would not be set properly for PS7 executables
* Changed some of the language within the options page to be more descriptive.
* Fixed an issue where the WPF designer would not load in VS2022 on certain environments.
* Fixed an issue where Script Analyzer Quick Fixes would not work in VS2022
* Added support for format document (Ctrl+K, Ctrl+D)
* Fixed an issue where the form designer would save files as ANSI rather than UTF8
* Fixed an issue where cls or Clear-Host would cause the terminal prompt to disappear in the PowerShell Interactive Window.
* Added support for compiling Linux executables in Visual Studio
* Fixed an issue where WPF event handlers could be generated incorrectly for generic parameter types
* Fixed an issue where the PowerShell Interactive window buffer width would not adjust when the window size changed
* Added support for icons in PS7 executables
* Added support for obfuscating PS7 executables

## PowerShell Pro Tools Module

* Fixed an issue where packaging for Linux would not work
* Added support for icons in PS7 executables
* Added support for obfuscating PS7 executables

# 2022.1.0

Released: 2022-01-11

## PowerShell Tools for Visual Studio

* Fixed an issue where the settings page would crash if PSScriptAnalyzer was not installed
* Fixed an issue where ProductVersion was set incorrectly in MSBuild
* Fixed an issue where PowerShell 7 executables would not have file properties
* Fixed an issue where you could not browse for application icons
* Added support for the WPF Designer in Visual Studio 2022
* Fixed an issue where the WPF designer IntelliSense would not work in VS 2019

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where PowerShell 7 executables would not have file properties

## PSScriptPad

* Added Save All button
* Fixed an issue where PowerShell 7 executables would not have file properties
* Added About dialog.

## PowerShell Pro Tools Module

* Fixed an issue where PowerShell 7 executables would not have file properties

# 2022.12.3

Released: 2022-01-05

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where the IronmanPowerShellWinFormsHost wouldn't run anything

# 2021.12.3

Released: 2021-12-27

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where packaging a PowerShell 7.2 or later executable could result in a failure to build

## PowerShell Pro Tools Module

* Fixed an issue where packaging a PowerShell 7.2 or later executable could result in a failure to build

# 2021.12.2

Released: 2021-12-27

## PowerShell Tools for Visual Studio

* Fixed an issue when switching between PowerShell 7 and Windows PowerShell could cause VS to hang
* Fixed an issue where pressing escape to cancel IntelliSense would clear the line in the PowerShell Interactive Window
* Fixed an issue where the PowerShell Interactive Window did not support ANSI escape characters in PowerShell 7.2
* Fixed an issue where the the PowerShell 7 profile would not be loaded properly.
* Fixed an issue where packaging a PowerShell 7.2 or later executable could result in a failure to build

# 2021.12.2

Released: 2021-12-21

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where an attempt to load missing assemblies would be made.

## PowerShell Pro Tools Module

* Fixed an issue where an attempt to load missing assemblies would be made.

# 2021.12.1

Released: 2021-12-17

## PowerShell Tools for Visual Studio

* Fixed an issue where packaging an executable into an output directory with an apostrophe does not work.
* Fixed an issue where PS7.1 and PS7.2 output directories would contain all unpackaged files

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where packaging an executable into an output directory with an apostrophe does not work.
* Fixed an issue where PS7.1 and PS7.2 output directories would contain all unpackaged files

## PSScriptPad

* Fixed an issue where packaging an executable into an output directory with an apostrophe does not work.
* Fixed an issue where PS7.1 and PS7.2 output directories would contain all unpackaged files

## PowerShell Pro Tools Module

* Fixed an issue where packaging an executable into an output directory with an apostrophe does not work.
* Fixed an issue where PS7.1 and PS7.2 output directories would contain all unpackaged files

# 2021.12.0

Released: 2021-12-14

## PowerShell Tools for Visual Studio

* Fixed an issue where adding multiple form items would attempt to add multiple Resource.resx files
* Implemented a new settings dialog for Script Analyzer
* Added a new setting to change the behavior of script analyzer to only run on save
* Fixed an issue where Go To Definition would not work consistently
* Fixed an issue where post-build events would not run
* Added support for packaging PowerShell 7.2 and .NET 6.0 executables
* Added support for renaming the output executable

## PowerShell Pro Tools for Visual Studio Code

* Added support for packaging PowerShell 7.2 and .NET 6.0 executables
* Added support for renaming the output executable

## PSScriptPad

* Improved startup performance of PSScriptPad
* Fixed an issue where you couldn't view the options dialog when a Windows Form was open
* Fixed a race condition that could cause the debugger to hang was running a selection
* Added support for packaging PowerShell 7.2 and .NET 6.0 executables
* Added support for renaming the output executable
* Added an option to generate Windows Forms event handlers as functions

## PowerShell Pro Tools Module

* Added support for packaging PowerShell 7.2 and .NET 6.0 executables
* Added support for renaming the output executable

# 2021.11.1

Released: 2021-11-15

## PowerShell Tools for Visual Studio

* Fixed an issue where the form designer would not add the required references in Visual Studio 2022.

# 2021.11.1

Released: 2021-11-09

## PowerShell Pro Tools for Visual Studio Code

* Reduced the size of the extension by 80%
* Windows ARM platform support
* Support for bundling PowerShell 7.1 scripts
* Support for the Microsoft PowerShell Preview extension v3
* Support for signing executables

# 2021.11.0

Released: 2021-11-09

## PowerShell Tools for Visual Studio

* Support for Visual Studio 2022 GA
* Fixed an issue where parameter splatting refactor would not work in all scenarios
* PowerShell 7.1 packaging support

## PSScriptPad

* Fixed an issue where script analyzer would highlight too many lines
* Add Scratch Pad feature
* Add support for packaging PowerShell 7.1 scripts
* Fixed an issue where you would be unable to stop long running scripts

## PowerShell Pro Tools Module

* Added support for bundling PowerShell 7.1 scripts
* Added the ability to sign executables

# 2021.10.1

Released: 2021-10-18

## PSScriptPad

* Fixed an issue where saving a file a second time would not work
* Added logging mechanism to PSScriptPad

# 2021.10.0

Released: 2021-10-12

## PowerShell Tools for Visual Studio

* Added [refactoring tools](../powershell-pro-tools-documentation/visual-studio-code/refactoring.md)
* Fixed an issue where the $DTE variable was missing
* Added support for Pester 5 in the test adapter
* Fixed an issue where the package as executable command was missing in the solution explorer

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where PSScriptPad would hang when saving a large file
* Fixed an issue where the default WPF XAML would not work
* PSScriptPad will now open the designer and the form

## PSScriptPad

* Fixed an issue where PSScriptPad would hang when saving a large file
* Fixed an issue where the default WPF XAML would not work
* PSScriptPad will now open the designer and the form

## PowerShell Pro Tools Module

* Updated to the latest version of PSScriptPad

# 2021.9.2

Released: 2021-09-23

## PowerShell Tools for Visual Studio

* Fixed an issue where build events would not run

# 2021.9.1

Released: 2021-09-15

## PowerShell Tools for Visual Studio

* Fixed an issue where colors would be incorrect in dark themes
* Fixed an issue where the packager would show a failure to load NewtonSoft.Json
* Fixed an issue where WPF event handlers would be generated incorrectly

# 2021.9.0

Released: 2021-09-14

## PowerShell Tools for Visual Studio

* Visual Studio 2022 Support
* Fixed an issue where debugging a script could say that a pre-req was missing
* Fixed pre-req installation
* Fixed an issue where the Convert To PowerShell and Convert To C# commands were missing in the context menu
* Fixed an error that would be shown when attempting to package a script in Visual Studio
* Fixed an MSBuild warning that was shown when compiling on Windows
* Added support for bundling additional XAML files in executables
* Fixed an issue where using the .NET 5 SDK would cause executables to fail to build on Windows
* Added settings dialog under View \ PowerShell \ Settings

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where packaging in VS Code would use the wrong PowerShell SDK and fail to find modules
* Fixed an issue where the Upgrade-Module functionality would silently fail
* Fixed an MSBuild warning that was shown when compiling on Windows
* Added support for bundling additional XAML files in executables
* Fixed an issue where using the .NET 5 SDK would cause executables to fail to build on Windows
* Added support for switching the .NET SDK to use for packaging.

## PSScriptPad

* Fixed an MSBuild warning that was shown when compiling on Windows
* Added support for bundling additional XAML files in executables
* Fixed an issue where using the .NET 5 SDK would cause executables to fail to build on Windows

## PowerShell Pro Tools Module

* Fixed an MSBuild warning that was shown when compiling on Windows
* Added support for bundling additional XAML files in executables
* Fixed an issue where using the .NET 5 SDK would cause executables to fail to build on Windows
* Added support for switching the .NET SDK used to build executables

# 5.30.1

Released: 2021-08-06

## PowerShell Pro Tools for Visual Studio Code

* Added better error handling to console host to prevent packaged applications from crashing and to provide a meaningful error

# 5.30.0

Released: 2021-08-05

## PowerShell Pro Tools for Visual Studio Code

* Added support for excluding automatic variables from variables view

# 5.29.4

Released: 2021-07-27

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where DataGridView columns could not be added to the form designer

# 5.13.3

Released: 2021-07-27

## PSScriptPad

* Fixed an issue where DataGridView columns could not be added to the form designer

# 5.9.3

Released: 2021-07-27

## PowerShell Pro Tools Module

* Fixed an issue where DataGridView columns could not be added to the form designer

# 5.29.3

Released: 2021-07-22

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where the packager would fail when the script name had a space in it

# 5.13.2

Released: 2021-07-22

## PSScriptPad

* Fixed an issue where the packager would fail when the script name had a space in it

# 5.10.2

Released: 2021-07-22

## PowerShell Tools for Visual Studio

* Fixed an issue where the packager would fail when the script name had a space in it

# 5.9.2

Released: 2021-07-22

## PowerShell Pro Tools Module

* Fixed an issue where the packager would fail when the script name had a space in it

# 5.29.2

Released: 2021-07-21

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where an exception could be thrown during packaging.

# 5.13.1

Released: 2021-07-21

## PSScriptPad

* Fixed an issue where an exception could be thrown during packaging.

# 5.10.1

Released: 2021-07-21

## PowerShell Tools for Visual Studio

* Fixed an issue where an exception could be thrown during packaging.

# 5.9.1

Released: 2021-07-21

## PowerShell Pro Tools Module

* Fixed an issue where an exception could be thrown during packaging.

# 5.29.1

Released: 2021-07-20

## PowerShell Pro Tools for Visual Studio Code

* Added support for bundling resources into executables

# 5.13.0

Released: 2021-07-20

## PSScriptPad

* Added support for bundling resources into executables

# 5.10.0

Released: 2021-07-20

## PowerShell Tools for Visual Studio

* Added support for bundling resources into executables

# 5.9.0

Released: 2021-07-20

## PowerShell Pro Tools Module

* Added support for bundling resources into executables

# 5.29.0

Released: 2021-07-09

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where the extension would not activate
* Fixed an issue where workspace analysis could prevent other features of the extension from work in tandem
* Fixed an issue where the History node was slow

# 5.28.10

Released: 2021-07-08

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where the PowerShellProTools.Host.exe process would constantly use CPU
* Added support for packaging PowerShell 7.0.6

# 5.12.3

Released: 2021-07-08

## PSScriptPad

* Added support for packaging PowerShell 7.0.6

# 5.8.11

Released: 2021-07-08

## PowerShell Pro Tools Module

* Added support for packaging PowerShell 7.0.6

# 5.28.9

Released: 2021-07-07

## PowerShell Pro Tools for Visual Studio Code

* Updated to latest .NET Core SDK to remediate CVE-2021-26701

# 5.28.8

Released: 2021-07-05

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where Rename Symbol (F2) would incorrectly rename variables
* Fixed a performance issue with workspace analysis

# 5.9.9

Released: 2021-06-16

## PowerShell Tools for Visual Studio

* Fixed an issue where Read-Host would not work

# 5.28.7

Released: 2021-06-15

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where the extension could fail to load on some Windows system

# 5.28.6

Released: 2021-06-14

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where the extension could fail to load in large workspaces
* Fixed an issue where PSScriptPad would crash when pressing Ctrl+C

# 5.12.2

Released: 2021-06-14

## PSScriptPad

* Fixed an issue where PSScriptPad would crash when pressing Ctrl+C

# 5.28.5

Released: 2021-06-03

## PowerShell Pro Tools for Visual Studio Code

* Add support for disabling QuickEdit during packaging
* Fixed an issue with the packager and strings with single quotes

# 5.12.1

Released: 2021-06-03

## PSScriptPad

* PSScriptPad layout now persists
* Add support for disabling QuickEdit during packaging
* Fixed an issue with the packager and strings with single quotes

# 5.8.10

Released: 2021-06-03

## PowerShell Pro Tools Module

* Add support for disabling QuickEdit during packaging
* Fixed an issue with the packager and strings with single quotes

# 5.28.4

Released: 2021-06-02

## PowerShell Pro Tools for Visual Studio Code

* Fixed a packaging issue with concatenated strings and Join-Path

# 5.11.5

Released: 2021-06-02

## PSScriptPad

* Fixed a packaging issue with concatenated strings and Join-Path

# 5.9.8

Released: 2021-06-02

## PowerShell Tools for Visual Studio

* Fixed a packaging issue with concatenated strings and Join-Path

# 5.8.9

Released: 2021-06-02

## PowerShell Pro Tools Module

* Fixed a packaging issue with concatenated strings and Join-Path

# 5.28.3

Released: 2021-06-01

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue with extension activation
* Fixed an issue with generating ImageLists in PSScriptPad resources

# 5.11.4

Released: 2021-06-01

## PSScriptPad

* Fixed an issue with ImageList resources would not be stored correctly

# 5.9.6

Released: 2021-05-26

## PowerShell Tools for Visual Studio

* Fixed an issue where the extension would not activate in VS 2017

# 5.9.5

Released: 2021-05-25

## PowerShell Tools for Visual Studio

* Fixed an issue where the variables window would not work if opened after the main extension package activated

# 5.9.4

Released: 2021-05-24

## PowerShell Tools for Visual Studio


# 5.11.3

Released: 2021-05-21

## PSScriptPad

* Added copy and paste to the Windows Form designer

# 5.9.3

Released: 2021-05-21

## PowerShell Tools for Visual Studio

* Fixed an issue where bundling form resources would not work correctly

# 5.28.1

Released: 2021-05-20

## PowerShell Pro Tools for Visual Studio Code

* Fixed a crash on startup in PSScriptPad
* Resolved a performance issue where analysis would run twice in PSScriptPad

# 5.11.2

Released: 2021-05-20

## PSScriptPad

* Fixed a crash on startup in PSScriptPad
* Resolved a performance issue where analysis would run twice in PSScriptPad

# 5.11.1

Released: 2021-05-19

## PSScriptPad

* Fixed an issue with Out-GridView

# 5.9.2

Released: 2021-05-19

## PowerShell Tools for Visual Studio

* Fixed an issue with Out-GridView

# 5.28.0

Released: 2021-05-18

## PowerShell Pro Tools for Visual Studio Code

* Updated version of PSScriptPad
* Added Open with PSScriptPad to PS1 files navigation bar
* Added F2 Rename Variables

# 5.11.0

Released: 2021-05-18

## PSScriptPad

* PSScriptAnalyzer support
* Fixed an issue where errors and warnings would not show any text when hovered

# 5.27.3

Released: 2021-05-17

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where the extension would fail to activate on Linux and Mac OSX.

# 5.10.4

Released: 2021-05-17

## PSScriptPad

* Fixed an issue where the terminal cursor was barely visible
* Fixed an issue where the terminal cursor would lose focus after executing a command
* Added a Grid to the default WPF window so controls are draggable by default

# 5.8.8

Released: 2021-05-17

## PowerShell Pro Tools Module

* Fixed an issue with running Merge-Script on Linux

# 5.9.1

Released: 2021-05-14

## PowerShell Tools for Visual Studio

* Added Modules window
* Improved performance of the variables window

# 5.9.0

Released: 2021-05-13

## PowerShell Tools for Visual Studio

* Added Variables window
* Consolidated PowerShell tools windows into a PowerShell sub menu

# 5.27.2

Released: 2021-05-12

## PowerShell Pro Tools for Visual Studio Code

* Updated PSScriptPad version
* Removed custom telemetry setting to rely on the built-in, opt-in VS Code setting

# 5.27.1

Released: 2021-05-11

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where the extension could hang during activation

# 5.8.12

Released: 2021-05-11

## PowerShell Tools for Visual Studio

* Fixed an issue where the bundler could throw an error and fail when bundling certain modules.

# 5.27.0

Released: 2021-05-10

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where string resources would not be output in the form design
* Fixed an issue where the extension could fail to activate
* Added Jobs explorer and management

# 5.10.3

Released: 2021-05-10

## PSScriptPad

* Fixed an issue with the WPF designer where it would lose focus on the current control when changing props

# 5.10.1

Released: 2021-05-10

## PSScriptPad

* Fixed an issue where string resources would not be output in the form designer

# 5.8.11

Released: 2021-05-10

## PowerShell Tools for Visual Studio

* Fixed an issue where the packager would throw an error about NewtonSoft.Json when bundling modules.

# 5.26.0

Released: 2021-05-07

## PowerShell Pro Tools for Visual Studio Code

* Added session explorer
* Added pin and unpin session commands

# 5.8.10

Released: 2021-05-05

## PowerShell Tools for Visual Studio

* Added Execute Selection button to PowerShell Toolbar

# 5.25.0

Released: 2021-05-04

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where the VS Code module wouldn't load properly
* Fixed an issue with several links within the extension
* Added support for custom tree views
* Added history view to PowerShell Explorer

# 5.8.9

Released: 2021-05-04

## PowerShell Tools for Visual Studio

* Removed a dependency on NewtonSoft.Json that was causing a problem when compiling scripts to executables

# 5.24.3

Released: 2021-05-03

## PowerShell Pro Tools for Visual Studio Code

* Improved extension activation performance
* Improved status bar message icon visibility

# 5.8.8

Released: 2021-05-03

## PowerShell Tools for Visual Studio

* Fixed an issue with packaging PS7 scripts containing a ternary operator

# 5.24.2

Released: 2021-04-30

## PowerShell Pro Tools for Visual Studio Code

* Added namespaces to the reflection view
* Added a command for loading assemblies into the reflection view

# 5.8.7

Released: 2021-04-30

## PowerShell Tools for Visual Studio

* Fixed an issue where resource files would not be generated when paths contained periods

# 5.24.1

Released: 2021-04-29

## PowerShell Pro Tools for Visual Studio Code

* Added type decompiler to Reflection view
* Improved field and property information in Reflection view.

# 5.24.0

Released: 2021-04-28

## PowerShell Pro Tools for Visual Studio Code

* Added Reflection view

# 5.23.0

Released: 2021-04-27

## PowerShell Pro Tools for Visual Studio Code

* Added Sign on Save feature

# 5.10.0

Released: 2021-04-27

## PSScriptPad

* Added integrated mode

# 5.8.6

Released: 2021-04-26

## PowerShell Tools for Visual Studio

* Fixed an issue with packaging XAML files.

# 5.22.4

Released: 2021-04-23

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue with activation caching
* Fixed an issue with packaging PowerCLI

# 5.9.11

Released: 2021-04-23

## PSScriptPad

* Fixed an issue with activation caching
* Fixed an issue with packaging PowerCLI

# 5.8.5

Released: 2021-04-23

## PowerShell Tools for Visual Studio

* Fixed an issue with activation caching
* Fixed an issue with ImageList controls in the form designer
* Fixed an issue with packaging PowerCLI

## PowerShell Pro Tools Module

* Fixed an issue with activation caching
* Fixed an issue with packaging PowerCLI

# 5.22.3

Released: 2021-04-21

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where packaging modules could cause an Access Denied error

# 5.9.10

Released: 2021-04-21

## PSScriptPad

* Fixed an issue where packaging modules could cause an Access Denied error

# 5.8.4

Released: 2021-04-21

## PowerShell Tools for Visual Studio

* Fixed an issue where packaging modules could cause an Access Denied error

# 5.8.3

Released: 2021-04-21

## PowerShell Pro Tools Module

* Fixed an issue where packaging modules could cause an Access Denied error

# 5.22.2

Released: 2021-04-14

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where packaging would use the wrong PowerShell version when looking up modules causing certain modules to fail to load

# 5.9.7

Released: 2021-04-14

## PSScriptPad

* Fixed an issue where packaging would use the wrong PowerShell version when looking up modules causing certain modules to fail to load

# 5.8.2

Released: 2021-04-14

## PowerShell Tools for Visual Studio

* Fixed an issue where packaging would use the wrong PowerShell version when looking up modules causing certain modules to fail to load

## PowerShell Pro Tools Module

* Fixed an issue where packaging would use the wrong PowerShell version when looking up modules causing certain modules to fail to load

# 5.22.1

Released: 2021-04-07

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where the Introduce Using refactoring could cause the PowerShell Pro Tools host to stop responding
* Removed an unnecessary and noisy log message.
* Updated the version of PSScriptPad

# 5.9.6

Released: 2021-04-07

## PSScriptPad

* Fixed an issue where PSScriptPad would unnecessarily allocate a console and cause a hang on some machines.

# 5.8.1

Released: 2021-04-07

## PowerShell Tools for Visual Studio

* Fixed an issue where the extension would fail to install due to a expired certificate

## PowerShell Pro Tools Module

* Updated the version of PSScriptPad

# 5.22.0

Released: 2021-04-05

## PowerShell Pro Tools for Visual Studio Code

* Added 'Open PSCommander Configuration' Command

# 5.21.1

Released: 2021-03-03

## PowerShell Pro Tools for Visual Studio Code


# 5.21.0

Released: 2021-03-01

## PowerShell Pro Tools for Visual Studio Code

* Added support for building .NET Core based Windows Services with PowerShell 7

# 5.8.0

Released: 2021-03-01

## PowerShell Tools for Visual Studio

* Added support for building .NET Core based Windows Services with PowerShell 7

## PowerShell Pro Tools Module

* Added support for building .NET Core based Windows Services with PowerShell 7

# 5.20.10

Released: 2021-02-11

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where packaging would not work with modules that contained a C# .cs file (like MSAL.PS)

# 5.9.5

Released: 2021-02-11

## PSScriptPad

* Fixed an issue where packaging would not work with modules that contained a C# .cs file (like MSAL.PS)

# 5.7.22

Released: 2021-02-11

## PowerShell Tools for Visual Studio

* Fixed an issue where packaging would not work with modules that contained a C# .cs file (like MSAL.PS)

# 5.7.5

Released: 2021-02-11

## PowerShell Pro Tools Module

* Fixed an issue where packaging would not work with modules that contained a C# .cs file (like MSAL.PS)

# 5.20.9

Released: 2021-02-09

## PowerShell Pro Tools for Visual Studio Code

* Added support for Packaging on Mac OSX

# 5.7.4

Released: 2021-02-09

## PowerShell Pro Tools Module

* Added support for Packaging on Mac OSX

# 5.20.8

Released: 2021-02-08

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where arguments would not be passed to packaged scripts running PowerShell 7
* Added support for [Packaging on Linux](../powershell-pro-tools-documentation/packaging/packaging-on-linux.md)

# 5.7.3

Released: 2021-02-08

## PowerShell Pro Tools Module

* Fixed an issue where arguments would not be passed to packaged scripts running PowerShell 7
* Added support for [Packaging on Linux](../powershell-pro-tools-documentation/packaging/packaging-on-linux.md)

# 5.20.7

Released: 2021-01-31

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where an error could be shown in the console when navigating PowerShell scripts.

# 5.20.6

Released: 2021-01-25

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where an error would be shown when the VS Code automation feature could not connect properly

# 5.7.21

Released: 2021-01-25

## PowerShell Tools for Visual Studio


# 5.20.5

Released: 2021-01-21

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where an invalid link would be shown in the hover provider.

# 5.7.20

Released: 2021-01-20

## PowerShell Tools for Visual Studio

* Fixes an issue where stepping through a Switch would fail to step properly.

# 5.7.2

Released: 2021-01-15

## PowerShell Pro Tools Module

* Updated to the latest version of PSScriptPad.

# 5.20.4

Released: 2021-01-14

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where Generate Proxy Function would run on empty command names and show an error in the terminal
* PSScriptPad now persists loaded WPF assembly locations so they are loaded when the application is restarted

# 5.9.4

Released: 2021-01-14

## PSScriptPad

* PSScriptPad now persists loaded WPF assembly locations so they are loaded when the application is restarted

# 5.20.3

Released: 2021-01-12

## PowerShell Pro Tools for Visual Studio Code

* Added toolbox support for the WPF designer in PSScriptPad

# 5.9.3

Released: 2021-01-12

## PSScriptPad

* Added toolbox support for the WPF designer in PSScriptPad

# 5.20.2

Released: 2021-01-11

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where PSScriptPad could crash when opening a XAML file

# 5.9.2

Released: 2021-01-11

## PSScriptPad

* Fixed an issue where PSScriptPad could crash when opening a XAML file

# 5.20.1

Released: 2021-01-10

## PowerShell Pro Tools for Visual Studio Code


# 5.20.0

Released: 2021-01-10

## PowerShell Pro Tools for Visual Studio Code

* Added support for the [PSScriptPad WPF Designer](/broken/pages/-MQh81XqMmK37OjdJCdy)

# 5.9.1

Released: 2021-01-10

## PSScriptPad


# 5.9.0

Released: 2021-01-10

## PSScriptPad

* Added WPF Designer

# 5.19.10

Released: 2021-01-04

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where Generate Proxy Function would show errors in the terminal

# 5.7.19

Released: 2021-01-04

## PowerShell Tools for Visual Studio

* Fixed an issue where stepping through a ForEach loop would fail to step properly

# 5.19.9

Released: 2020-12-31

## PowerShell Pro Tools for Visual Studio Code

* Added [Generate Proxy Function ](../powershell-pro-tools-documentation/visual-studio-code/refactoring.md#generate-proxy-function)refactoring
* Fixed an issue with convert to $_ and convert to $PSItem refactorings

# 5.7.18

Released: 2020-12-30

## PowerShell Tools for Visual Studio

* Fixed an issue where constrained language mode would fail silently.

# 5.19.8

Released: 2020-12-28

## PowerShell Pro Tools for Visual Studio Code

* Added [Enhanced Hover](../powershell-pro-tools-documentation/visual-studio-code/enhanced-hover.md) support
* Fixed an issue where the Variable Explorer would cause a memory leak

# 5.19.7

Released: 2020-12-27

## PowerShell Pro Tools for Visual Studio Code

* Fixed issue with Split Pipeline refactoring changing the functionality of a script
* Added integration into VS Code refactoring provider system
* Added [Convert to $PSItem](../powershell-pro-tools-documentation/visual-studio-code/refactoring.md#convert-to-usdpsitem) refactoring
* Added [Convert to $_](../powershell-pro-tools-documentation/visual-studio-code/refactoring.md#convert-to-usd_) refactoring
* Fixed an issue where Split Pipeline would show on one-command pipelines

# 5.19.6

Released: 2020-12-26

## PowerShell Pro Tools for Visual Studio Code

* Added [Split Pipeline ](../powershell-pro-tools-documentation/visual-studio-code/refactoring.md#split-pipeline)refactoring
* Added [Introduce Using Namespace ](../powershell-pro-tools-documentation/visual-studio-code/refactoring.md#introduce-using-namespace)refactoring

# 5.8.3

Released: 2020-12-26

## PSScriptPad

* Fixed an issue where PSScriptPad would crash when using Save As

# 5.19.5

Released: 2020-12-25

## PowerShell Pro Tools for Visual Studio Code

* Reorganized tree view providers
* Added Help and Information node
* Fixed an issue where an error could be shown if the tree view was clicked before the extension was fully loaded
* Added options for hiding tree view providers
* Added an option to enable module update checks (now disabled by default) as it was slow on many machines

# 5.8.2

Released: 2020-12-24

## PSScriptPad

* Added option for Font Size
* Fixed a crash that would happen when setting a breakpoint after saving a new file
* Added support for package.psd1 config files
* Added support for opening and saving PSM1 and PSD1 files
* Fixed an issue where output from the package process would not be shown

# 5.19.4

Released: 2020-12-23

## PowerShell Pro Tools for Visual Studio Code

* Added support for the PowerShell Preview extension

# 5.8.1

Released: 2020-12-21

## PSScriptPad

* Fixed an issue with the console running commands in the wrong runspace
* Fixed a display issue with the terminal

# 5.19.3

Released: 2020-12-18

## PowerShell Pro Tools for Visual Studio Code

* Added [Reorder Parameters](../powershell-pro-tools-documentation/visual-studio-code/refactoring.md#reorder-parameters)

# 5.19.2

Released: 2020-12-17

## PowerShell Pro Tools for Visual Studio Code

* Added [Generate Function from Usage ](../powershell-pro-tools-documentation/visual-studio-code/refactoring.md#generate-function-from-usage)Refactoring

# 5.8.0

Released: 2020-12-16

## PSScriptPad

* Settings are now stored in the registry
* Added a setting for overriding the machine's execution policy
* Fixed an issue where errors would be thrown when attempting to view variables in Windows PowerShell

# 5.19.1

Released: 2020-12-15

## PowerShell Pro Tools for Visual Studio Code

* Added [Convert To Multiline Command](../powershell-pro-tools-documentation/visual-studio-code/refactoring.md#convert-to-multiline-command) Refactoring

# 5.19.0

Released: 2020-12-14

## PowerShell Pro Tools for Visual Studio Code

* Added [Run in new Terminal](../powershell-pro-tools-documentation/visual-studio-code/debugging/start-in-new-terminal.md)
* Added [Refactoring](../powershell-pro-tools-documentation/visual-studio-code/refactoring.md)

# 5.18.0

Released: 2020-12-13

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where variables wouldn't work in PowerShell 7.1
* Fixed an issue where Out-VSCodeGridView wouldn't work in PowerShell 7.1
* Added a command to insert paths from [Provider Explorer](../powershell-pro-tools-documentation/visual-studio-code/powershell-explorer.md#provider-explorer)
* Added a command to view child items of a path in [Provider Explorer](../powershell-pro-tools-documentation/visual-studio-code/powershell-explorer.md#provider-explorer)
* Added a command to view item properties in [Provider Explorer](../powershell-pro-tools-documentation/visual-studio-code/powershell-explorer.md#provider-explorer)

# 5.7.17

Released: 2020-12-12

## PowerShell Tools for Visual Studio

* Fixed an issue with the locals and watch window when using PowerShell 7.1

# 5.7.16

Released: 2020-12-11

## PowerShell Tools for Visual Studio

* Fixed an issue where copy and paste would not work as expected when debugging with the REPL window open

# 5.7.1

Released: 2020-12-10

## PowerShell Pro Tools Module

* Fixed an issue where Global Hotkeys could cause the PowerShell process to crash
* Added an -ArgumentList parameter to the Set-HotKey cmdlet

# 5.7.0

Released: 2020-12-09

## PowerShell Pro Tools Module

* Added support for [Global Hotkeys](../powershell-pro-tools-documentation/powershell-module/global-hotkeys.md).

# 5.17.2

Released: 2020-12-08

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where ignored elements were case sensitive
* Added support for expanding paths in strings
* Added support for ignoring paths

# 5.17.1

Released: 2020-12-07

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where RapidSense wouldn't refresh caches after changing settings
* Added Ignored Variables setting to RapidSense
* Fixed an issue where the PowerShell Pro Tools module wouldn't be imported correctly

# 5.17.0

Released: 2020-12-06

## PowerShell Pro Tools for Visual Studio Code

* Added [RapidSense](../powershell-pro-tools-documentation/visual-studio-code/rapidsense.md)

# 5.16.11

Released: 2020-12-05

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where the profiler failing to return results
* Added millisecond timing to the profiler

# 5.7.14

Released: 2020-12-04

## PowerShell Tools for Visual Studio


# 5.16.10

Released: 2020-12-03

## PowerShell Pro Tools for Visual Studio Code


# 5.7.13

Released: 2020-12-03

## PowerShell Tools for Visual Studio

* Fixed an issue where script analysis could fail after a script was saved with syntax errors
* Fixed an issue with the WPF event binding service where it would fail silently when an event handler was added to a control without a name.
* Fixed an issue with the WPF event binding service where it would generate functions with unapproved verbs

# 5.6.8

Released: 2020-12-03

## PowerShell Pro Tools Module


# 5.16.9

Released: 2020-12-02

## PowerShell Pro Tools for Visual Studio Code

* Changed purchasing links to point to new store
* Fixed an issue where collections would not expand correctly.

# 5.7.7

Released: 2020-12-02

## PSScriptPad


# 5.7.12

Released: 2020-11-30

## PowerShell Tools for Visual Studio

* Fixed an issue where variable expansion would not work correctly for objects that were IEnumerable but did not generic

# 5.7.11

Released: 2020-11-27

## PowerShell Tools for Visual Studio

* Fixed an issue where expanding a collection in the variable window with a single value wouldn't work.

# 5.7.10

Released: 2020-11-23

## PowerShell Tools for Visual Studio

* Fixed an issue where the PowerShell version drop down wouldn't show the current version

# 5.16.7

Released: 2020-11-21

## PowerShell Pro Tools for Visual Studio Code

* Added support for [scoped package.psd1 files](../powershell-pro-tools-documentation/visual-studio-code/packaging-in-visual-studio-code.md#scoped-package-psd1)

# 5.7.9

Released: 2020-11-21

## PowerShell Tools for Visual Studio

* Fixed an issue where debugging wouldn't stop on breakpoints in PowerShell 7.1
* Removed the Reset PowerShell Session option because it caused many problems when enabled.

# 5.7.6

Released: 2020-11-21

## PSScriptPad


# 5.16.6

Released: 2020-11-16

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where the packager could fail when packaging certain Windows PowerShell modules.

# 5.7.8

Released: 2020-11-16

## PowerShell Tools for Visual Studio

* Fixed an issue where the analysis service could fail to start
* Fixed an issue where the packager could fail when packaging certain Windows PowerShell modules.

# 5.6.7

Released: 2020-11-16

## PowerShell Pro Tools Module

* Fixed an issue where the packager could fail when packaging certain Windows PowerShell modules.

# 5.16.5

Released: 2020-11-09

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where the PoshTools extension would fail to load if the user profile contained spaces.

# 5.16.4

Released: 2020-11-04

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue with packaging the NTFSSecurity module

# 5.7.7

Released: 2020-11-04

## PowerShell Tools for Visual Studio

* Fixed an issue with packaging the NTFSSecurity module

# 5.7.5

Released: 2020-11-04

## PSScriptPad

* Fixed an issue with packaging the NTFSSecurity module

# 5.6.6

Released: 2020-11-04

## PowerShell Pro Tools Module

* Fixed an issue with packaging the NTFSSecurity module

# 5.16.3

Released: 2020-10-30

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where the packager would state that there was unreachable code detected

# 5.16.2

Released: 2020-10-28

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where the profile would run within the PoshTools host process rather than in the PowerShell process.

# 5.16.1

Released: 2020-10-26

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where packaging would fail with a duplicate assembly error

# 5.7.6

Released: 2020-10-26

## PowerShell Tools for Visual Studio

* Fixed an issue where script analysis would fail to start due to a threading issue
* Fixed an issue where the packager would state that there was unreachable code detected

# 5.7.5

Released: 2020-10-26

## PowerShell Tools for Visual Studio

* Fixed an issue where packaging would fail with a duplicate assembly error

# 5.16.0

Released: 2020-10-20

## PowerShell Pro Tools for Visual Studio Code

* Added support for Mac OS

# 5.7.4

Released: 2020-10-19

## PowerShell Tools for Visual Studio

* Fixed an issue where building with certain project types could result in a Visual Studio crash.

# 5.15.4

Released: 2020-10-15

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue with bundling modules that contained System.Management.Automation.dll
* Fixed an issue with bundling modules that contained RootModules nested in a folder

# 5.7.3

Released: 2020-10-15

## PowerShell Tools for Visual Studio

* Fixed an issue with bundling modules that contained System.Management.Automation.dll
* Fixed an issue with bundling modules that contained RootModules nested in a folder

# 5.7.2

Released: 2020-10-13

## PowerShell Tools for Visual Studio

* Improve extension startup performance

# 5.7.1

Released: 2020-10-08

## PowerShell Tools for Visual Studio

* Fixed a null reference exception when activating the extension

# 5.7.0

Released: 2020-10-07

## PowerShell Tools for Visual Studio

* [Go to definition support](../powershell-pro-tools-documentation/visual-studio/go-to-definition.md) for commands and functions

# 5.15.2

Released: 2020-09-29

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue in PSScriptPad where variables would not be shown during debugging.

# 5.7.4

Released: 2020-09-29

## PSScriptPad

* Fixed an issue where variables would not be shown during debugging.

# 5.15.1

Released: 2020-09-28

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue with bundling the ActiveDirectory module in PowerShell 7 standalone executables

# 5.6.4

Released: 2020-09-28

## PowerShell Tools for Visual Studio

* Fixed an issue where the error list line number would be off by one
* Fixed an issue with bundling the ActiveDirectory module in PowerShell 7 standalone executables

# 5.6.3

Released: 2020-09-24

## PowerShell Tools for Visual Studio

* Fixed an issue where compiling a PowerShell 7 executable that included WinForms wouldn't work if Hide Console Window was unchecked.

# 5.6.2

Released: 2020-09-22

## PowerShell Tools for Visual Studio

* Fixed an issue where parse errors would not be highlighed
* Fixed an issue where clicking a parse or analysis error in the error list would throw an exception
* Fixed an issue with the NumericDropDown Windows Form component would not be generated correctly.

# 5.15.0

Released: 2020-09-21

## PowerShell Pro Tools for Visual Studio Code

* Support for Linux

# 5.14.1

Released: 2020-09-17

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue with packaging Windows Forms applications with PS7

# 5.6.1

Released: 2020-09-17

## PowerShell Tools for Visual Studio

* Fixed an issue with packaging Windows Forms applications with PS7

# 5.14.0

Released: 2020-09-16

## PowerShell Pro Tools for Visual Studio Code

* Added support for packaging the 7.0.2 and 7.0.3 PowerShell SDK

# 5.6.0

Released: 2020-09-16

## PowerShell Tools for Visual Studio

* Added support for packaging the 7.0.2 and 7.0.3 PowerShell SDK

# 5.13.1

Released: 2020-09-13

## PowerShell Pro Tools for Visual Studio Code


# 5.7.2

Released: 2020-09-13

## PSScriptPad


# 5.5.7

Released: 2020-09-13

## PowerShell Tools for Visual Studio


# 5.13.0

Released: 2020-09-01

## PowerShell Pro Tools for Visual Studio Code

* Added "Generate Tool" command

# 5.12.11

Released: 2020-09-01

## PowerShell Pro Tools for Visual Studio Code

* Updated to the latest version of PSScriptPad
* Fixed an issue with Form Generation where it would generate forms with common parameters

# 5.5.6

Released: 2020-09-01

## PowerShell Tools for Visual Studio

* Fixed an issue where script analyzer support could cause a hang when changing languages or starting Visual Studio

# 5.5.5

Released: 2020-08-05

## PowerShell Tools for Visual Studio

* Reverting changes in version 5.5.4 that resulted in commands not executing correctly
* Fixed an issue with PSScriptAnaylzer support

# 5.5.4

Released: 2020-07-31

## PowerShell Tools for Visual Studio

* Fixed an issue where parser errors would be shown for PS7’s new features

# 5.7.1

Released: 2020-07-22

## PSScriptPad

* Fixed an issue where breakpoints would not be hit
* Fixed an issue where a document would not be activated when debugging.

# 5.7.0

Released: 2020-07-22

## PSScriptPad

* Added support for light and dark themes

# 5.12.10

Released: 2020-07-21

## PowerShell Pro Tools for Visual Studio Code

* PowerShell Pro Tools: Install PowerShell Pro Tools Module command
* Fixed an issue that would cause the extension to delay on startup and occasionally time out

# 5.12.9

Released: 2020-07-16

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue with PSScriptPad where the variables window wouldn’t expand variables correctly

# 5.6.7

Released: 2020-07-16

## PSScriptPad

* Fixed an issue with PSScriptPad where the variables window wouldn’t expand variables correctly

# 5.12.8

Released: 2020-07-15

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue that would cause a delay on start up

# 5.6.6

Released: 2020-07-15

## PSScriptPad

* Fixed an issue where internal logging would be shown in the console.

# 5.5.3

Released: 2020-07-14

## PowerShell Tools for Visual Studio

* Fixed an issue where the locals window wouldn’t display variables

# 5.12.5

Released: 2020-07-12

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where ListView, TreeView and ContextMenu child items would not work in PSScriptPad
* VS Code extension now installs the PowerShell module automatically so it loads correctly
* Fixed an issue where packaging would fail if a script ended in a comment
* Fixed an issue where packaging would fail if a script was too large
* Fixed an issue where the opacity setting wouldn’t work on form controls on certain systems.

# 5.6.4

Released: 2020-07-12

## PSScriptPad

* Fixed an issue where ListView, TreeView and ContextMenu child items would not work in PSScriptPad
* Fixed an issue where packaging would fail if a script ended in a comment
* Fixed an issue where packaging would fail if a script was too large
* Fixed an issue where the opacity setting wouldn’t work on form controls on certain systems.

# 5.5.2

Released: 2020-07-12

## PowerShell Tools for Visual Studio

* Fixed an issue where ListView, TreeView and ContextMenu child items would not work in PSScriptPad
* Fixed an issue where packaging would fail if a script ended in a comment
* Fixed an issue where packaging would fail if a script was too large
* Fixed an issue where the opacity setting wouldn’t work on form controls on certain systems.
* Fixed an issue where script analysis would highlight too much of the script when there was an issue
* Fixed an issue where script analysis quickfix items would replace too much of the script

# 5.12.5

Released: 2020-07-01

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where the PowerShell Pro Tools host process could lock up

# 5.12.4

Released: 2020-06-26

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where launching more than one version of VS Code would cause the extension to fail to connect

# 5.12.3

Released: 2020-06-24

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where the extension could fail to connect to the PowerShell process.

# 5.12.2

Released: 2020-06-23

## PowerShell Pro Tools for Visual Studio Code

* The provider tree view now runs within the main runspace.

# 5.12.1

Released: 2020-06-19

## PowerShell Pro Tools for Visual Studio Code

* Added Host Processes tree node with support for one-click debugging runspaces

# 5.12.0

Released: 2020-06-19

## PowerShell Pro Tools for Visual Studio Code

* Added an Output Channel for PowerShell Pro Tools diagnostics
* PowerShell Pro Tools now uses an external process rather than being hosted directly in PowerShell
* Fixed an issue where the PowerShell Pro Tools module would load over and over again
* Fixed an issue where the variable window would not show variables
* Fixed an issue with the form designer that wouldn’t be marked dirty when properties were edited
* Fixed an issue with the form designer where it wouldn’t save StatusStrip items
* Fixed an issue with the form designer where it wouldn’t change the main PS1’s form name if it was changed in the designer
* Fixed an issue with the profiler where it would not work if params or using statements were used.

# 5.6.3

Released: 2020-06-19

## PSScriptPad

* Fixed an issue with the form designer that wouldn’t be marked dirty when properties were edited
* Fixed an issue with the form designer where it wouldn’t save StatusStrip items
* Fixed an issue with the form designer where it wouldn’t change the main PS1’s form name if it was changed in the designer

# 5.5.1

Released: 2020-06-02

## PowerShell Tools for Visual Studio

* Fixed an issue where packaging would fail for projects created with 5.4.9 or older

# 5.11.0

Released: 2020-05-29

## PowerShell Pro Tools for Visual Studio Code

* Added support for packaging PowerShell 7 executables
* Added experimental support for packaging Linux and OSX executables

# 5.5.0

Released: 2020-05-26

## PowerShell Tools for Visual Studio

* Added support for packaging PowerShell 7 executables
* Added experimental support for packaging Linux and OSX executables
* Fixed an issue that could cause a crash if PSScriptAnalyzer was enabled
* Fixed an issue where QuickFix items could cause a crash when being executed

# 5.4.9

Released: 2020-05-18

## PowerShell Tools for Visual Studio

* Fixed a crash that could happen when PSScriptAnalyzer was enabled
* Fixed an issue that would cause breakpoints to not be hit when lines were indented

# 5.10.1

Released: 2020-05-06

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue with PSScriptPad that was causing hangs when running WinForm scripts.

# 5.6.2

Released: 2020-05-06

## PSScriptPad

* Fixed an issue that was causing hangs when running WinForm scripts.

# 5.4.8

Released: 2020-05-06

## PowerShell Tools for Visual Studio

* Fixed an issue where removing a breakpoint would not clear the breakpoint in PowerShell
* Fixed an issue where output could be written out of order

# 5.4.7

Released: 2020-05-06

## PowerShell Tools for Visual Studio

* Fixed an issue that was causing hangs when running WinForm scripts.

# 5.4.6

Released: 2020-04-30

## PowerShell Tools for Visual Studio

* Fixed an issue where stopping the debugger could prevent it from starting again
* Fixed an issue where using statements in a script would prevent it from packaging correctly
* Add logging to the packaging system to better diagnose issues.

# 5.4.5

Released: 2020-04-27

## PowerShell Tools for Visual Studio

* Fixed an issue with variables not expanding properly in the Locals and Watch windows.
* Fixed an issue with an exception being shown during startup due to the Analysis Service not being ready
* Fixed an issue with the output pane no longer showing script output
* Fixed an issue where terminating errors would not be shown

# 5.4.4

Released: 2020-04-19

## PowerShell Tools for Visual Studio

* Removed the experimental console for now as it was causing unexpected issues for some users.

# 5.10.0

Released: 2020-04-17

## PowerShell Pro Tools for Visual Studio Code

* Out-VSCodeGridView

# 5.9.0

Released: 2020-04-16

## PowerShell Pro Tools for Visual Studio Code

* Cmdlets for managing [VS Code with PowerShell](https://ironmansoftware.com/automating-visual-studio-code-with-powershell/)

# 5.4.2

Released: 2020-04-16

## PowerShell Tools for Visual Studio

* Fixed an issue where the extension would allocate a console window on startup
* The console window may be allocated outside of Visual Studio and the PowerShell Console (Experimental) window will cause VS to become unresponsive.

# 5.8.8

Released: 2020-04-14

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue with the variables view showing incorrect child items
* Improved the expansion of child items in the variables view
* Improved the generation of child item paths

# 5.4.1

Released: 2020-04-13

## PowerShell Tools for Visual Studio

* Fixed an issue with installation into Visual Studio 2017

# 5.4.0

Released: 2020-04-12

## PowerShell Tools for Visual Studio

* Added a new PowerShell Console window. Click View->Other Windows->PowerShell Console to open it.
* Removed dependency on gRPC to reduce hangs when using PoshTools
* Improved performance of the Attach to Process dialog when PoshTools is installed
* Fixed icons for PowerShell-based nodes in the solution explorer

# 5.8.7

Released: 2020-04-06

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where putting an apostrophe in a label would cause the Form Designer to fail to load
* Fixed an issue where copy and pasting text into PSScriptPad would cause it to crash

# 5.6.1

Released: 2020-04-06

## PSScriptPad

* Fixed an issue where putting an apostrophe in a label would cause the Form Designer to fail to load
* Fixed an issue where copy and pasting text into PSScriptPad would cause it to crash

# 5.8.6

Released: 2020-04-03

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue with the variable view not showing variables.

# 5.8.5

Released: 2020-03-27

## PowerShell Pro Tools for Visual Studio Code

* Added a $Service object to OnStart\OnStop for packaged services to access the ServiceBase for the service
* Added $ProcessArgs and $ServiceArgs variables to the runspace for packaged services
* Fixed an issue where $PSScriptRoot would not work for packaged services

# 5.6.0

Released: 2020-03-27

## PSScriptPad

* Added PSReadline Support

# 5.3.6

Released: 2020-03-27

## PowerShell Tools for Visual Studio

* Added a $Service object to OnStart\OnStop for packaged services to access the ServiceBase for the service
* Added $ProcessArgs and $ServiceArgs variables to the runspace for packaged services
* Fixed an issue where Execute Selection would not show up in folder view
* Fixed an issue where $PSScriptRoot would not work for packaged services
* Updated signing certificate

# 5.5.1

Released: 2020-03-22

## PSScriptPad

* Console Window
* Fixed an issue where WinForms would be hidden when running them from PSScriptPad.

# 5.5.0

Released: 2020-03-18

## PSScriptPad

* PowerShell 7 Support

# 5.8.4

Released: 2020-03-03

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where an error would be shown when loading the extension
* Fixed an error where loading the module tree would cause the extension to become unresponsive

# 5.3.5

Released: 2020-02-28

## PowerShell Tools for Visual Studio

* Fixed an issue where the solution directory would not be set when opening a solution or switching PowerShell versions
* Fixed issue where the $dte variable may not be present
* Fixed an issue where the service process would not log

# 5.8.3

Released: 2020-02-10

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where a failed packaging build would not show the error message in the output

# 5.4.4

Released: 2020-02-10

## PSScriptPad

* Fixed an issue where a failed packaging build would not show the error message in the output

# 5.3.4

Released: 2020-02-10

## PowerShell Tools for Visual Studio

* Added a Script property to the debug settings to allow for running a specific script rather than the currently open script
* Fixed an issue where a failed packaging build would not show the error message in the output

# 5.3.3

Released: 2020-02-04

## PowerShell Tools for Visual Studio

* Added a PowerShell Windows Forms Project template
* Fixed an issue when setting the platform for a packaged script
* Fixed an issue when setting the “PackagePowerShell” setting for a packaged script
* Fixed a syntax error with the Windows Forms item template

# 5.8.2

Released: 2020-01-31

## PowerShell Pro Tools for Visual Studio Code

* Added -ProductId to New-Installer
* Added -ScriptArguments to New-InstallerCustomAction
* Added an option to add a context menu item for opening PS1 files with PSScriptPad
* Added support for Comment (Ctrl+K,Ctrl+C) and Uncomment (Ctrl+K,Ctrl+U) keyboard shortcuts in PSScriptPad
* Added support for reloading files updated outside of PSScriptPad
* Fixed issue with installer shortcuts throwing an exception if a workingDirectory or arguments were not specified
* Fixed an issue where the installer shortcut working directory would not be specified correctly
* Fixed an issue where the installer shortcut would not use the correct PowerShell variable
* Fixed an issue where adding images to the installer UI on Windows PowerShell would throw an exception
* Fixed an issue where PSScriptPad would crash on startup.

# 5.4.2

Released: 2020-01-31

## PSScriptPad

* Added an option to add a context menu item for opening PS1 files with PSScriptPad
* Added support for Comment (Ctrl+K,Ctrl+C) and Uncomment (Ctrl+K,Ctrl+U) keyboard shortcuts
* Added support for reloading files updated outside of PSScriptPad
* Fixed a crash that could happen on startup due to a threading issue

# 5.8.1

Released: 2020-01-28

## PowerShell Pro Tools for Visual Studio Code

* Added support for WorkingDirectory on New-InstallerShortcut
* Added support for Arguments on New-InstallerShortcut
* Added support for Show on New-InstallerShortcut
* Added support for Arguments on New-InstallerCustomAction
* Fixed issue where packaged applications wouldn’t work with arguments with spaces
* Fixed issue with installer cmdlets not resolving paths correctly
* When specifying a shortcut for an installer, if it’s a PS1, it will automatically launch PowerShell.exe rather than targeting the script

# 5.4.1

Released: 2020-01-28

## PSScriptPad

* Fixed issue where packaged applications wouldn’t work with arguments with spaces

# 5.3.2

Released: 2020-01-28

## PowerShell Tools for Visual Studio

* Fixed issue with resource generation in Visual Studio Windows Forms Designer
* Fixed issue where packaged applications wouldn’t work with arguments with spaces

# 5.8.0

Released: 2020-01-22

## PowerShell Pro Tools for Visual Studio Code


# 5.3.1

Released: 2020-01-22

## PowerShell Tools for Visual Studio


# 5.7.1

Released: 2020-01-21

## PowerShell Pro Tools for Visual Studio Code

* PowerShellProTools module is now signed
* Fixed an issue with [PSScriptPad](https://ironmansoftware.com/psscriptpad/) that was preventing typing while IntelliSense was running in the terminal

# 5.3.2

Released: 2020-01-21

## PSScriptPad

* Splash screen
* Added restart\restart as admin buttons
* Options dialog
* Added ability to optimize startup speed
* Fixed an issue where setting a breakpoint would cause syntax highlighting to disappear
* Tool windows are auto-docked when opening a Windows Form

# 5.3.1

Released: 2020-01-21

## PSScriptPad

* PowerShellProTools module is now signed
* Fixed an issue with PSScriptPad that was preventing typing while IntelliSense was running in the terminal

# 5.2.5

Released: 2020-01-21

## PowerShell Tools for Visual Studio

* Fixed an issue with PowerShell Pro Tools initializing
* Depending on how the PowerShell Pro Tools extension was loaded an error would be shown and it would fail to loaded.

# 5.7.0

Released: 2020-01-18

## PowerShell Pro Tools for Visual Studio Code

* Support for generating resources such as images and icons for WinForms.
* Fixed issue with packaging resources used for WinForms.

# 5.3.0

Released: 2020-01-18

## PSScriptPad

* Support for generating resources such as images and icons for WinForms.
* Fixed issue with packaging resources used for WinForms.

# 5.2.4

Released: 2020-01-18

## PowerShell Tools for Visual Studio

* Fixed an issue with bundling resources
* Resources, such as images and icons, would not be bundled correctly when bundling a WinForm control.

# 5.2.3

Released: 2020-01-16

## PowerShell Tools for Visual Studio


# 5.6.6

Released: 2020-01-15

## PowerShell Pro Tools for Visual Studio Code


# 5.2.6

Released: 2020-01-15

## PSScriptPad


# 5.2.2

Released: 2020-01-15

## PowerShell Tools for Visual Studio

* Republished 5.2.1 as 5.2.2
* An issue with the marketplace was causing a failure when upgrading to 5.2.1. Republished as 5.2.2 and it seems to have resolved it.

# 5.2.1

Released: 2020-01-15

## PowerShell Tools for Visual Studio


# 5.6.5

Released: 2020-01-14

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where packaging config would not respect the platform property.

# 5.2.5

Released: 2020-01-14

## PSScriptPad

* Fixed an issue where the debugger would not start the second time

# 5.2.0

Released: 2020-01-14

## PowerShell Tools for Visual Studio

* Added Platform Settings to Packaging
* You can now specify the platform (x64\x86) when packaging executables.

# 5.6.4

Released: 2020-01-13

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where packaging would use a package.psd1 in the temp directory.

# 5.2.4

Released: 2020-01-13

## PSScriptPad

* Added support for Clear-Host
* Fixed an issue where the debugging status indicator would not advance correctly
* Fixed an issue where the terminal would be disabled if broken in the debugger
* Fixed an issue where output to the terminal would not appear on a new line
* Fixed an issue where you would need to invoke debugging commands twice (Step Over, Step Into, Continue, Stop)

# 5.6.3

Released: 2020-01-12

## PowerShell Pro Tools for Visual Studio Code

* Fixed an issue where packaging would throw an invalid format exception
* Fixed an issue with package architecture

# 5.2.3

Released: 2020-01-12

## PSScriptPad

* Fixed an issue where packaging would throw an invalid format exception
* Fixed an issue with package architecture

# 5.6.2

Released: 2020-01-10

## PowerShell Pro Tools for Visual Studio Code

* Added support for setting the architecture of the exectuable that is created when packaging
* Replaced Windows Form Designer with [PSScriptPad](https://ironmansoftware.com/psscriptpad/)
* Fixed an issue with ToolStrip items.
* Fixed an issue with deleting components

# 5.2.2

Released: 2020-01-10

## PSScriptPad

* Added a What’s New link that points to the changelog
* Fixed issue with strings in the variables tool window
* Fixed issue with terminal attempting to run commands while the runspace was busy
* Terminal now executes on a background thread so the UI doesn’t lock up
* Fixed an issue where the entire script would be collapsible.

# 5.6.1

Released: 2019-12-31

## PowerShell Pro Tools for Visual Studio Code

* Added breakpoint support to the Windows Form Designer
* Added stepping support to the Windows Form Designer
* Added support for stopping debugger to the Windows Form Designer
* Improved performance of IntelliSense
* Fixed a bug where the Windows Form Designer would lose code-behind changes on startup.

# 5.6.0

Released: 2019-12-28

## PowerShell Pro Tools for Visual Studio Code

* The Windows Forms Designer can now execute PowerShell to show the form you are designing.
* The Windows Forms Designer can now package the Windows Form as a executable
* An output window was added to the Windows Forms Designer so you can see the output from your PS scripts.

# 5.5.1

Released: 2019-12-20

## PowerShell Pro Tools for Visual Studio Code


# 5.5.0

Released: 2019-12-20

## PowerShell Pro Tools for Visual Studio Code

* The Windows Forms Designer properties and toolbox are now in a dockable tool window.
* The Windows Forms Designer now supports moving controls with the arrow keys.

# 5.4.6

Released: 2019-12-18

## PowerShell Pro Tools for Visual Studio Code

* Added a button to open the Windows Form Designer
* We’ve made it easier to open the Windows Form Designer from a PowerShell file. Just click the new Show Windows Form Designer button from your form.ps1 file.
* [![](https://i2.wp.com/ironmansoftware.com/wp-content/uploads/2019/12/show-winform.png?resize=570%2C351\&ssl=1)](https://i2.wp.com/ironmansoftware.com/wp-content/uploads/2019/12/show-winform.png?ssl=1)
* Fixed error message when executing commands
* In certain circumstances, when you would execute PowerShell Pro Tools commands, an E_PIPE error would be shown even though the command was completed successfully.

# 5.1.4

Released: 2019-11-21

## PowerShell Tools for Visual Studio

* Fixed Crash During Start up or Solution Load
* There was a race condition between the PowerShell host starting and the gRPC client being available to set the location of the REPL window. This would cause a crash when VS was starting and loading a PS solution at the same time.
* Fixed Crash when selecting PS Script Analyzer Rules
* When selecting PS Script Analyzer rules, there could be a condition where a directory needed to store the settings would not exist. This directory is now created before attempting to save the settings.
* Added STA Support for Windows PowerShell
* In the General options page, you can now select STA mode for Windows PowerShell. This primarily affects Windows Forms controls, like the web browser control, that rely on COM.

# 5.1.3

Released: 2019-11-19

## PowerShell Tools for Visual Studio

* Hang when running command-line tools
* Command-line tools that used the error stream (like git.exe) would cause a hang in the PowerShell debugger.

# 5.1.2

Released: 2019-11-18

## PowerShell Tools for Visual Studio

* Visual Studio: Fixed Aggressive Extension Loading
* The PoshTools extension was loading aggressively. It would load even when no PowerShell solution or interactive window was open.
* Visual Studio: Fixed exception in script analyzer
* When Visual Studio was loading, the script analyzer would attempt to analyze “null” file resulting in an error.
* Visual Studio: Added Convert to PowerShell command
* The Paste As command was replaced with Convert to PowerShell.

# 5.1.1

Released: 2019-11-15

## PowerShell Tools for Visual Studio

* Visual Studio: Visual Studio would hang when using PowerShell v3\v4
* When the PowerShell extension would initialize and PowerShell v3 or v4 was being used, the extension would cause the IDE to hang.
* Visual Studio: Debugging would not work in Visual Studio 2017
* The error “Attaching the PowerShell Debug Engine debugger to Process unknown process” would be shown when attempting to debug.
* Visual Studio: Breakpoint would not be set in Visual Studio 2017
* The debugger would not break on a breakpoint set in Visual Studio 2017.

# 5.1.0

Released: 2019-11-11

## PowerShell Tools for Visual Studio

* Visual Studio: Solution Wide Analysis
* [PowerShell Pro Tools](https://ironmansoftware.com/powershell-pro-tools/) now uses [PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer) to analyze all the scripts within your solution in the background. You will still see tags on the active file, but the error list will also report any issues with any PSM1 or PS1 files in your solution.
* ![](https://i2.wp.com/ironmansoftware.com/wp-content/uploads/2019/11/solution-wide-analysis.png?resize=961%2C626\&ssl=1)
* Visual Studio: PSScriptAnalyzer Settings
* You can now modify PSScriptAnalyzer settings directly in the PowerShell Tools Options. Go to the Analysis page to turn on Analysis, Solution Wide Analysis, enable specific levels or even turn off specific rules.
* ![](https://i2.wp.com/ironmansoftware.com/wp-content/uploads/2019/11/analysis-options.png?resize=1005%2C663\&ssl=1)
* Visual Studio Code: Fixed PowerShell Host Initialization
* The PowerShell Pro Tools host could fail to initialize so startup operations would not be performed putting the extension in an unknown state. The extension has been fixed to load the host consistenlty.
* Visual Studio Code: Fixed PowerShell Host Crash Reinitialization
* If the Visual Code PowerShell Host would crash, PowerShell Pro Tools would not reconnect to the PowerShell process. This would prevent it from working.
