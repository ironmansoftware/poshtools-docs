---
description: Packager PowerShell scripts as executables.
---

# PowerShell Packager

{% hint style="info" %}
Download from the [PowerShell Pro Tools download page](https://ironmansoftware.com/powershell-pro-tools/downloads).
{% endhint %}

The PowerShell Packager uses the same packaging tools as the PowerShell Pro Tools module and PowerShell Pro Tools for VS Code but provides a simple interface that does not require configuration files or special build tools. This tool currently only supports Windows PowerShell executables.&#x20;

Running the packager will provide a simple wizard that you can step through to provide details for the resulting executable.&#x20;

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

## Properties

### Root Script

The root script is the script that will run when the executable is run. You can dot source other scripts and import modules in this script. This script will also receive the parameters passed to the executable.&#x20;

### Package Referenced Scripts

Any dot-sourced script referenced in the root script will be packaged as well. If those scripts include other dot-sourced scripts, they will also be included and so on.&#x20;

### Package Referenced Modules

Any module imported with `Import-Module` will be included with the executable.&#x20;

### File Properties

These are the properties that will be set on the resulting executable. For example, File Version, Description and Company name.&#x20;

### Application Properties

These are properties of the application itself. These include hiding the console window and Windows UI support.&#x20;

### Output Path

&#x20;The folder path to output the resulting executable to.&#x20;

## Certificate

The certificate is optional and will cause the packager to call `Set-AuthenticodeSignature` against the executable. The certificate path should be a certificate provider path.

```powershell
Cert:\LocalMachine\My\1111DDDDD
```

## Diagnostic Logging

The packager will automatically write diagnostic logs to the following location.&#x20;

```powershell
$Env:LOCALAPPDATA\PowerShellTools\PSPackager
```
