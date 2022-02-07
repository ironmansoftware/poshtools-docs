---
description: Script analysis for PowerShell scripts.
---

# Analysis

{% hint style="info" %}
Requires a [PowerShell Pro Tools license](https://ironmansoftware.com/pricing/powershell-pro-tools).
{% endhint %}

PowerShell Pro Tools uses PSScriptAnalyzer to run static code analysis of PowerShell scripts in Visual Studio. You can enable analysis by click View->PowerShell->Settings. Click Save after modifying the settings.&#x20;

![Script Analyzer Settings](<../../.gitbook/assets/image (83) (1).png>)

On the options page, you can turn on and off script analyzer completely, manage solution wide analysis, disable specific severities or even specific rules.&#x20;

When Script Analyzer is enabled, squiggly lines will be present within source files to provide information on potential issues with the ability to provide quick fixes for those issues.&#x20;

If you have solution wide analysis enabled, you will be able to see errors within your entire solution within the Error List window.&#x20;

![Error List Window](<../../.gitbook/assets/image (8) (1).png>)

## Quick Fix

PowerShell Pro Tools supports quick fix actions provided by PSScriptAnalyzer. If the suggestion has a Suggested Correction, PowerShell Pro Tools will provide a Quick Action light bulb next to the line that needs to be addressed.&#x20;

![Executing quick fix actions](../../.gitbook/assets/quickfix.gif)
