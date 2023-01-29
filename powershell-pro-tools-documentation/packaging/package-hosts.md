---
description: Learn about the different ways to host your PowerShell scripts.
---

# Package Hosts

## Default Host&#x20;

The default host uses the .NET SDK to compile an executable that runs your PowerShell script. The default host currently provides more options than the other hosts but is often flagged as suspicious by anti-virus applications. It also requires the .NET SDK installed on the local machine in order to function.&#x20;

You do not need to make any changes to use the default host.&#x20;

## Ironman Software Host

The Ironman Software host is a precompiled executable that is updated to include your script and settings. It does not require the .NET SDK and is less likely to be flagged by antivirus.&#x20;

To use the Ironman Software PowerShell host, you will need to set the Host property in `package.psd1` to the `IronmanPowerShellHost` or `IronmanPowerShellWinFormsHost`.&#x20;

The different between the standard host and the Win Forms host is that the latter will hide the console window.&#x20;

### Supported Features

A subset of the packaging features is supported by the Ironman Software host.

* Script Bundling and Packaging
* Automatic Module Bundling and Packaging
* File Information (Version, Description, Company, etc)&#x20;
* Custom Application Icon
* Windows PowerShell
* Hidden Console Window&#x20;

Features that are not supported include:

* PowerShell 7
* Obfuscation
* Services
* Resources

