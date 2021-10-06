---
description: Getting started with PowerShell Protect.
---

# Getting Started

{% embed url="https://www.youtube.com/watch?v=ocYtcaeWiQQ" %}

PowerShell Protect can be installed from the PowerShell Gallery. 

```text
Install-Module PowerShellProtect
```

To install the AMSI provider that is used to audit and block scripts, you will need to run the following command. 

{% hint style="info" %}
This command needs to be run as administrator. 
{% endhint %}

```text
Install-PowerShellProtect
$Configuration = New-PSPConfiguration 
Set-PSPConfiguration -Configuration $Configuration -FileSystem
```

Once installed, the [Default Rules](rules.md#default-rules) will be enabled. You can also enable additional rules using the PowerShell Protect configuration cmdlets. 

For example, this configuration will block and audit any script that contains a command with `webrequest` in the name. 

```text
$Condition = New-PSPCondition -Property "command" -contains -Value "webrequest"
$BlockAction = New-PSPAction -Block
$FileAction = New-PSPAction -File -Format "{applicationName},{rule}" -Path "%temp%\audit.csv" -Name 'File'
$Rule = New-PSPRule -Name "Web Request" -Condition $Condition -Action @($BlockAction, $FileAction)

$Configuration = New-PSPConfiguration -Rule $Rule
Set-PSPConfiguration -Configuration $Configuration -FileSystem
```

