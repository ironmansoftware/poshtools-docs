# Uninstallation

To completely remove PSCommander, first clear its configuration while PSCommander is still running. This lets PSCommander unregister the shortcuts, file associations, Explorer context-menu entries, and custom protocols that it manages.

Back up the configuration, replace it with an empty configuration, and wait a few seconds for PSCommander to reload it.

```powershell
$configPath = Join-Path ([Environment]::GetFolderPath('MyDocuments')) 'PSCommander\config.ps1'
Copy-Item -LiteralPath $configPath -Destination "$configPath.bak" -Force
Set-Content -LiteralPath $configPath -Value '# PSCommander configuration removed'
Start-Sleep -Seconds 2
```

If PSCommander is not running, start it and wait for it to initialize before clearing the configuration.

```powershell
Start-Commander
```

Disable its logon startup entry, stop the process, and remove every installed version of the module.

```powershell
Uninstall-Commander -ErrorAction SilentlyContinue
Stop-Commander -ErrorAction SilentlyContinue
Uninstall-Module PSCommander -AllVersions
```

Finally, remove the saved configuration and local database. This permanently deletes the configuration backup and all PSCommander settings and registration data.

```powershell
Remove-Item -LiteralPath (Join-Path ([Environment]::GetFolderPath('MyDocuments')) 'PSCommander') -Recurse -Force
Remove-Item -LiteralPath (Join-Path ([Environment]::GetFolderPath('ApplicationData')) 'PSCommander') -Recurse -Force
```
