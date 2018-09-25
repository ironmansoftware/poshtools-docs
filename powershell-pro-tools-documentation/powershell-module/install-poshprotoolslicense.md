---
external help file: PowerShellToolsPro.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
---

# Install-PoshProToolsLicense

## SYNOPSIS
Installs a PowerShell Pro Tools license.

## SYNTAX

```
Install-PoshProToolsLicense -License <String>
```

## DESCRIPTION
Installs a PowerShell Pro Tools license.

## EXAMPLES

### Example 1
```
PS C:\> Install-PoshProToolsLicense -License "<License><Terms>asdfas</Terms></License>"
```

Installs the specified PowerShell Pro Tools license.

## PARAMETERS

### -License
License to install.
This should be the content of the license and not a path.

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

