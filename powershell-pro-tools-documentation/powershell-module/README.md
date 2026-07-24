# PowerShell Module

The PowerShell Pro Tools PowerShell module provides command-line access to packaging and Windows Forms design tooling. It is useful for local scripts, repeatable build steps, and CI systems where you do not want to drive an editor.

## Features

* Bundle dot-sourced scripts into a single script with `Merge-Script`.
* Package scripts as executables with a `package.psd1` configuration.
* Generate Windows Forms code from PowerShell functions with `ConvertTo-WinForm`.
* Launch the Windows Forms designer with `Show-WinFormDesigner`.
* Open PSScriptPad with `Show-PSScriptPad`.

## Quick Examples

Install the module from the PowerShell Gallery.

```powershell
Install-Module PowerShellProTools
```

Bundle a script and its dot-sourced dependencies.

```powershell
Merge-Script -Config @{
    Root = ".\Start-Tool.ps1"
    OutputPath = ".\out"
    Bundle = @{
        Enabled = $true
        Modules = $true
    }
}
```

Open a script in the Windows Forms designer.

```powershell
Show-WinFormDesigner -Path .\MainForm.ps1
```

## More Information

* [Changelog](https://github.com/ironmansoftware/powershell-pro-tools/releases)
* [Installation](installation.md)
* [System Requirements](system-requirements.md)
* [Packaging](../packaging/README.md)
* [PowerShell Gallery](https://www.powershellgallery.com/packages/PowerShellProTools)

