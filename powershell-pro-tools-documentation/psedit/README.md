# PSEdit

PSEdit is a terminal-based editor for PowerShell and common text-based configuration files. It runs from PowerShell and provides a focused editing experience without leaving the terminal.

Use PSEdit when you need a lightweight editor for scripts, JSON, YAML, XML, Markdown, or plain text files in a shell-first workflow.

## Features

* PowerShell IntelliSense.
* Syntax highlighting for PowerShell, JSON, YAML, XML, Markdown, and plain text.
* PowerShell script execution.
* Error and syntax error views.
* Format on save for supported file types.
* Custom themes through `psedit.json`.

## Quick Examples

Start the editor.

```powershell
Show-PSEditor
```

Open a file.

```powershell
Show-PSEditor -Path .\build.ps1
```

Use the alias.

```powershell
psedit .\settings.json
```

Run the current PowerShell script with `F5`, run a selection with `F8`, or run and exit with `Ctrl+Shift+F5`.

## Formatting PowerShell

PowerShell formatting requires PSScriptAnalyzer.

```powershell
Install-Module PSScriptAnalyzer
```

## More Information

* [Changelog](https://github.com/ironmansoftware/psedit/releases)
* [Installation](installation.md)
* [System Requirements](system-requirements.md)
* [GitHub](https://github.com/ironmansoftware/psedit)
* [PowerShell Gallery](https://www.powershellgallery.com/packages/psedit)
