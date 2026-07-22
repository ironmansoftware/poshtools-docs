# System Requirements

## PowerShell

* Windows PowerShell 5.1 or PowerShell 7.
* PowerShellGet or PSResourceGet configured for the PowerShell Gallery.

## Packaging

Packaging requirements depend on the runtime you target.

| Target PowerShell | .NET target |
| ----------------- | ---------- |
| Windows PowerShell | .NET Framework 4.6.2 or later Developer Pack |
| PowerShell 7.2 | .NET 6 SDK |
| PowerShell 7.3 | .NET 7 SDK |
| PowerShell 7.4 | .NET 8 SDK |

The packaging process may need access to NuGet.org or an internal NuGet feed to restore runtime packages. See [Package.psd1](../packaging/package.psd1.md) for supported package configuration values.

## Windows Forms

Windows Forms designer and packaged Windows Forms applications require Windows.
