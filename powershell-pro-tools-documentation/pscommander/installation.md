# Installation

PSCommander is distributed through the PowerShell Gallery.

```powershell
Install-Module PSCommander
```

To install without administrator permissions, use the current-user scope.

```powershell
Install-Module PSCommander -Scope CurrentUser
```

## Start PSCommander

Create the starter configuration and launch PSCommander.

```powershell
Start-Commander
```

## Run at Logon

Register PSCommander to run when the user logs on.

```powershell
Install-Commander
```

Remove the logon registration with `Uninstall-Commander`.

```powershell
Uninstall-Commander
```
