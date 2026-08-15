# Installation

PSMSI is distributed through the PowerShell Gallery.

```powershell
Install-Module PSMSI
```

To install without administrator permissions, use the current-user scope.

```powershell
Install-Module PSMSI -Scope CurrentUser
```

## Update

```powershell
Update-Module PSMSI
```

## Verify Installation

```powershell
Import-Module PSMSI
Get-Command -Module PSMSI
```
