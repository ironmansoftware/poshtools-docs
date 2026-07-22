# System Requirements

## PowerShell

* Windows PowerShell 5.1 or PowerShell 7.
* PowerShellGet or PSResourceGet configured for the PowerShell Gallery.

## Operating System

* Windows is required to build and validate MSI packages.

## Installer Engine

PSMSI includes WiX Toolset v3 binaries and uses them to compile generated WiX XML into MSI packages. You do not need to install WiX separately for the standard module workflow.

## Build Inputs

* Files referenced by `New-InstallerFile` must exist at build time.
* Per-machine installers and installers targeting protected locations require elevation when installed.
