---
description: Installation information for PowerShell Protect.
---

# Installation

PowerShell Protect is distributed as a PowerShell module. You can install it from the PowerShell Gallery.&#x20;

## Install

Install the module and then register the PowerShell Protect AMSI provider using `Install-PowerShellProtect`. Registering the provider must be run as a local administrator.&#x20;

```powershell
Install-Module 'PowerShellProtect'
Install-PowerShellProtect
```

To install the module for the current user before registering the provider, use `-Scope CurrentUser`.

```powershell
Install-Module 'PowerShellProtect' -Scope CurrentUser
Install-PowerShellProtect
```

## Uninstall

Unregister the provider by using `Uninstall-PowerShellProtect`. This action must be run as a local administrator.&#x20;

```powershell
Uninstall-PowerShellProtect
```

Restart the machine after uninstalling to ensure the AMSI provider is fully unloaded before removing the module.
