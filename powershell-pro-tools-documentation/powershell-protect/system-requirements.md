# System Requirements

## Operating System

* Windows 10 or later.
* Windows Server 2016 or later.

PowerShell Protect registers an AMSI provider and is supported on Windows versions that provide the required AMSI infrastructure.

## PowerShell

* Windows PowerShell 5.1.
* PowerShell 7.
* PowerShellGet or PSResourceGet configured for the PowerShell Gallery.

## Permissions

* Local administrator permissions are required to run `Install-PowerShellProtect`.
* Local administrator permissions are required to run `Uninstall-PowerShellProtect`.

## Configuration Storage

Configuration can be stored in one of the following locations.

* Registry configuration value.
* Registry configuration file path.
* `%ProgramData%\PowerShellProtect\config.xml`.
