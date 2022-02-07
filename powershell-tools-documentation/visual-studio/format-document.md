---
description: Code formatting for PowerShell.
---

# Format Document

{% hint style="info" %}
Available in PowerShell Tools for Visual Studio 2022.2.0 or later. Requires a [PowerShell Pro Tools license](https://ironmansoftware.com/pricing/powershell-pro-tools).&#x20;
{% endhint %}

Code formatting can be accomplished by using the standard `Ctrl+K`, `Ctrl+D` keyboard shortcut within Visual Studio.&#x20;

The PSScriptAnalyzer module is required to perform formatting. From Windows PowerShell, you can install PSScriptAnalyzer with `Install-Module`.&#x20;

```powershell
Install-Module 'PSScriptAnalyzer' -Scope CurrentUser
```
