---
description: Audit and block PowerShell scripts on Windows.
---

# PowerShell Protect

{% hint style="success" %}
Check out PowerShell Protect on [GitHub](https://github.com/ironmansoftware/powershell-protect).
{% endhint %}

PowerShell Protect provides auditing and blocking support for Windows PowerShell and PowerShell on Windows machines. It integrates with the Antimalware Scan Interface (AMSI) so scripts can be evaluated before they execute in any PowerShell host.

Use PowerShell Protect when you need configurable policy enforcement for PowerShell script execution, including built-in detections for common bypass and exploitation techniques.

![](<../../.gitbook/assets/image (65).png>)

## Features

* Configurable blocking policies.
* Configurable audit policies.
* Audit output to file, HTTP, TCP, UDP, and event log actions.
* Built-in blocking rules for common suspicious PowerShell techniques.
* Windows PowerShell and PowerShell 7 support.
* File system or registry-backed configuration.

## Quick Example

```powershell
Install-Module PowerShellProtect
Install-PowerShellProtect

$Condition = New-PSPCondition -Property "command" -contains -Value "webrequest"
$BlockAction = New-PSPAction -Block
$Rule = New-PSPRule -Name "Web Request" -Condition $Condition -Action $BlockAction
$Configuration = New-PSPConfiguration -Rule $Rule -Action $BlockAction

Set-PSPConfiguration -Configuration $Configuration -FileSystem
```

Test a configuration before installing it.

```powershell
Test-PSPConfiguration -ConfigurationPath ".\config.xml" -ScriptBlock { Invoke-WebRequest }
```

## More Information&#x20;

* [Installation](installation.md)
* [System Requirements](system-requirements.md)
* [Getting Started](getting-started.md)
* [Download](https://www.powershellgallery.com/packages/PowerShellProtect)
