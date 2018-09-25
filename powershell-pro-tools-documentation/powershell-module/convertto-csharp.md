---
external help file: PowerShellToolsPro.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
---

# ConvertTo-CSharp

## SYNOPSIS
Converts PowerShell script to C# code.

## SYNTAX

### PathByPipeline
```
ConvertTo-CSharp -PowerShellScriptFile <FileInfo>
```

### Path
```
ConvertTo-CSharp -PowerShellScriptPath <String>
```

### Text
```
ConvertTo-CSharp -PowerShellScript <String>
```

### ScriptBlock
```
ConvertTo-CSharp -ScriptBlock <ScriptBlock>
```

## DESCRIPTION
Converts PowerShell script to C# code. You can specify a path, PowerShell script text or a PowerShell script block.

## EXAMPLES

### Example 1
```
PS C:\> ConvertTo-CSharp -PowerShellScriptPath .\*.ps1
```

Converts all PS1 files in the current directory to C# code. Returns an array of the contents of the files.

### Example 2
```
PS C:\> ConvertTo-CSharp -PowerShellScript "Get-Process"
```

Converts the specified PowerShell script to C# code.

### Example 3
```
PS C:\> ConvertTo-CSharp -ScriptBlock { Get-Process }
```

Converts the specified PowerShell ScriptBlock to C# code.

### Example 4
```
PS C:\> Get-ChildItem .\*.ps1 | ConvertTo-CSharp 
```

Converts the piped PS1 files to C#

## PARAMETERS

### -PowerShellScriptFile
A FileInfo for a PS1 or PSM1

```yaml
Type: FileInfo
Parameter Sets: PathByPipeline
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PowerShellScript
The contents of a PowerShell script

```yaml
Type: String
Parameter Sets: Text
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PowerShellScriptPath
The path to a PS1 or PSM1 file.

```yaml
Type: String
Parameter Sets: Path
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -ScriptBlock
A PowerShell ScriptBlock

```yaml
Type: ScriptBlock
Parameter Sets: ScriptBlock
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

### System.String
System.Management.Automation.ScriptBlock


## OUTPUTS

### System.String

## NOTES

## RELATED LINKS

