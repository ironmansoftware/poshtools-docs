# Installation

PSEdit is distributed through the PowerShell Gallery.

```powershell
Install-Module psedit
```

To install without administrator permissions, use the current-user scope.

```powershell
Install-Module psedit -Scope CurrentUser
```

## Optional Formatting Dependency

Install PSScriptAnalyzer to enable PowerShell formatting.

```powershell
Install-Module PSScriptAnalyzer
```

## Verify Installation

```powershell
Import-Module psedit
Get-Command Show-PSEditor
Get-Alias psedit
```
