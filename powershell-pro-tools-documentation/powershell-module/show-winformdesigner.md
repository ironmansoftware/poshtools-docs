# Show-WinFormDesigner



{% hint style="info" %}
Requires [PowerShell Pro Tools](https://ironmansoftware.com/poshtools)
{% endhint %}

## SYNOPSIS

Shows the Windows Form designer.

## SYNTAX

```text
Show-WinFormDesigner -DesignerFilePath <String> -CodeFilePath <String> [-EditorPipeName <String>] [-Theme <String>]
```

## DESCRIPTION

Shows the Windows Form designer. 

## EXAMPLES

### Example 1

```text
PS C:\> Show-WinFormDesigner -DesignerFilePath .\form.designer.ps1 -CodeFilePath .\form.ps1
```

Opens the Windows Form designer and loads the form.designer.ps1 form. 

## PARAMETERS

### -DesignerFilePath

The path to the designer PS1. This file should not be edited by hand.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CodeFilePath

The path to the code PS1 that will contain the event handlers for the form designer.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EditorPipeName

A named pipe to connect to the allow interaction with an editor. This is used by the VS Code extension.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Theme

The VS Code theme file to use. This should be the full path to a VS Code theme file. 

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

