---
description: Automate Visual Studio Code with PowerShell
---

# Automating Visual Studio Code

## Overview

Using PowerShell Pro Tools for Visual Studio Code you can automate the editor itself. This allows you to script repetitive actions you may take within Visual Studio Code. You can edit documents, show information and more. 

## Getting Started

To automate Visual Studio Code, you will need to first import the PowerShell Pro Tools VS Code module .

```text
PS C:\> Import-Module PowerSHellProTools.VSCode
```

Once the module is loaded, you can begin running commands. 

```text
PS C:\> Get-VSCodeTerminal


Name            : pwsh
Id              : 1
Columns         : 0
Rows            : 0
CreationOptions :  - C:\Program Files\PowerShell\7\pwsh.exe

Name            : PowerShell Integrated Console
Id              : 2
Columns         : 140
Rows            : 13
CreationOptions : PowerShell Integrated Console - C:\Program Files\PowerShell\7\pwsh.exe
```

## Available Commands

**Opening Documents** 

Open documents by file name.

```text
PS C:\> Open-VSCodeTextDocument -FileName .\form.designer.ps1
```

**Closing Text Editors**

Close editors that are already open.

```text
PS C:\> Get-VSCodeTextEditor | Remove-VSCodeTextEditor
```

**Getting Document Text**

Get the text of a document. You can also pass in a range to select only a partial section of the text.

```text
PS C:\> Get-VSCodeTextDocument | Get-VSCodeTextDocumentText
```

**Inserting Text**

Inserts text into a particular position in the selected document. This creates an edit but does not save the file.

```text
PS C:\> $position = New-VSCodePosition -Line 0 -Character 2
PS C:\> Get-VSCodeTextDocument | Add-VSCodeTextDocumentText -Position $position -Text NewText
```

**Removing Text**

Removes a range of text from a document. This creates an edit but does not save the file.

```text
PS C:\> $Range = New-VSCodeRange -StartLine 0 -EndLine 0 -StartCharacter 0 -EndCharacter 10
PS C:\> Get-VSCodeTextDocument | Remove-VSCodeTextDocumentText -Range $Range
```

**Setting Text Decorations**

Decorates a range of text with an optional set of colors, outlines, borders, and text.

```text
PS C:\> $Range = New-VSCodeRange -StartLine 0 -EndLine 0 -StartCharacter 0 -EndCharacter 55
PS C:\> Get-VSCodeTextEditor | Set-VSCodeTextEditorDecoration -BackgroundColor 'descriptionForeground' -Range $Range -Key 12321 -FontWeight bold
```

You can clear decorations by using the Clear-VSCodeTextEditorDecoration cmdlet. If you want to only clear a single decoration, you can specify the key.

[![](https://i1.wp.com/ironmansoftware.com/wp-content/uploads/2020/04/decoration.png?resize=669%2C155&ssl=1)](https://i1.wp.com/ironmansoftware.com/wp-content/uploads/2020/04/decoration.png?ssl=1)

**Sending Text to a Terminal**

Sends text to the specified terminal. You can commit this text by including the -AddNewLine parameter.

```text
PS C:\> Get-VSCodeTerminal | Where-Object Name -eq 'PowerShell Integrated Console' | Send-VSCodeTerminalText -Text 'Write-Host "Hello World!"'
```

[![](https://i2.wp.com/ironmansoftware.com/wp-content/uploads/2020/04/sendtext.png?resize=1260%2C82&ssl=1)](https://i2.wp.com/ironmansoftware.com/wp-content/uploads/2020/04/sendtext.png?ssl=1)

**Showing Messages**

Show a message to the user. You can show information, warning, and error messages.

```text
PS C:\> Show-VSCodeMessage -Message 'Error!!!' -Type Error
```

[![](https://i2.wp.com/ironmansoftware.com/wp-content/uploads/2020/04/error.png?resize=609%2C89&ssl=1)](https://i2.wp.com/ironmansoftware.com/wp-content/uploads/2020/04/error.png?ssl=1)

**Showing a Message with a Response**

Show a message to the user and provide an option for them to select.

```text
PS C:\> Show-VSCodeMessage -Message 'What should we do?' -Items @('Party', 'Sleep')
```

[![](https://i0.wp.com/ironmansoftware.com/wp-content/uploads/2020/04/showmessagewithoptions.png?resize=589%2C129&ssl=1)](https://i0.wp.com/ironmansoftware.com/wp-content/uploads/2020/04/showmessagewithoptions.png?ssl=1)

**Showing a Quick Pick List**

Shows a quick pick list for a user to select items from. This cmdlet will return the user’s selection to PowerShell.

```text
PS C:\> Show-VSCodeQuickPick -PlaceHolder 'What should we do?' -Items @('Party', 'Sleep')
```

[![](https://i0.wp.com/ironmansoftware.com/wp-content/uploads/2020/04/quicklist.png?resize=800%2C166&ssl=1)](https://i0.wp.com/ironmansoftware.com/wp-content/uploads/2020/04/quicklist.png?ssl=1)

**Showing an Input Box**

Shows an input box for the user to enter arbitrary text. This cmdlet will return the result to PowerShell.

```text
PS C:\> Show-VSCodeInputBox -PlaceHolder 'Enter some text'
```

[![](https://i1.wp.com/ironmansoftware.com/wp-content/uploads/2020/04/inputbox.png?resize=815%2C124&ssl=1)](https://i1.wp.com/ironmansoftware.com/wp-content/uploads/2020/04/inputbox.png?ssl=1)

**Set Status Bar Message**

Sets the status bar message.

```text
PS C:\> Set-VSCodeStatusBarMessage -Message 'Hellllloooo'
```

[![](https://i0.wp.com/ironmansoftware.com/wp-content/uploads/2020/04/statusbar.png?resize=797%2C100&ssl=1)](https://i0.wp.com/ironmansoftware.com/wp-content/uploads/2020/04/statusbar.png?ssl=1)

