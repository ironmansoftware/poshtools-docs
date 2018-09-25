---
external help file: PowerShellToolsPro.Cmdlets.dll-Help.xml
online version: null
schema: 2.0.0
---

# Merge-Script

## SYNOPSIS

Packages, bundles and\or obfuscates scripts.

## SYNTAX

```
Merge-Script -Script <String> [-OutputPath <String>] [-Bundle] [-Package] [-Obfuscate]

Merge-Script -Config <Hashtable>

Merge-Script -ConfigFile <String>
```

## DESCRIPTION

Packages, bundles and\or obfuscates scripts. Packaging and bundling are not mutually exclusive. Obfuscation  
requires packaging.

## EXAMPLES

### Example 1

```
PS C:\> Merge-Script -Script .\MyScript.ps1 -Output .\ -Package
```

Packages MyScript.ps1 into MyScript.exe and then outputs it to .\

### Example 2

```
PS C:\> Merge-Script -Script .\MyScript.ps1 -Output .\Bundle -Bundle
```

Bundles MyScript.ps1 and any scripts it dot sources into a single file and outputs it to .\Bundle.

### Example 3

```
PS C:\> Merge-Script -Script .\MyScript.ps1 -Output .\Bundle -Bundle -Package
```

Bundles MyScript.ps1 and any scripts it dot sources into a single file and then packages it into MyScript.exe and outputs it to .\Bundle.

### Example 4

```
PS C:\> Merge-Script -Script .\MyScript.ps1 -Output .\Bundle -Bundle -Package -Obfuscate
```

Bundles MyScript.ps1 and any scripts it dot sources into a single file and then packages it into MyScript.exe and outputs it to .\Bundle. The resulting executable will be obfuscated.

## PARAMETERS

### -Bundle

Bundles the script with dot sourced scripts found in the script.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Config

Config hashtable. More information found on about\_MergeScriptConfig.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigFile

Config file. More information found on about\_MergeScriptConfig.

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

### -Obfuscate

Obfuscate the .NET executable and PowerShell script.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputPath

The output path for the resulting script or executable.  
This should be a directory.

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

### -Package

Package the script as a .NET executable.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Script

The script to package in an executable and optionally bundle with other scripts.

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

## INPUTS

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS



