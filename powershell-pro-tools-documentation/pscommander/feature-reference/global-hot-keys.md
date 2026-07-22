# Global Hot Keys

PSCommander allows you to associate global hot keys to PowerShell actions.

This example defines a hot key that is invoked whenever the `Ctrl+T` key combination is pressed. Key combinations cannot interfere with other pre-existing combinations.

```powershell
New-CommanderHotKey -Key 'T' -ModifierKey 'Ctrl' -Action {
    Start-Process notepad
}
```
