---
description: Licensing for PowerShell Protect.
---

# License

PowerShell Protect requires a PowerShell Pro Tools or PowerShell Protect license. You can request a trial or purchase a license from [our website](https://www.ironmansoftware.com). Each active user using PowerShell Protect will require a license.&#x20;

## Free Features

[Default rules](rules.md#default-rules) do not require a license and will be enabled without configuration. You can optionally choose which rules are enforced. PowerShell Protect will log to the event log in the event of a rule being triggered.&#x20;

## Install a License

### Configuration&#x20;

You can include the license with your configuration. Pass the contents of the license file to `New-PSPConfiguration`

```powershell
New-PSPConfiguration -License "<license></license>"
```

### Installation Folder

The license should be included in the module installation directory and named `license.lic`.&#x20;

![](<../../.gitbook/assets/image (82) (1) (1).png>)

