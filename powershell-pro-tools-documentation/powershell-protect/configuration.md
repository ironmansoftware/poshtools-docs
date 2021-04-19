# Configuration

Configuration of PowerShell Protect is done using XML. You can create the XML file in the following locations. 

## Cmdlets

You can use the configuration cmdlets to get, set and test your Protect configurations. 

### Set-PSPConfiguration

To set a configuration for the local machine, you can use `Set-PSPConfiguration`. You will need to provide a path to a Protect configuration file and then the destination of the configuration. 

The below will install the configuration file into the file system location. 

```text
Set-PSPConfiguration -ConfigurationFilePath .\config.xml -FileSystem
```

The below will install the configuration file into the registry. 

```text
Set-PSPConfiguration -ConfigurationFilePath .\config.xml -Registry
```

You can also pass a Configuration object created with `New-PSPConfiguration` to `Set-PSPConfiguration`.

```text
$Config = New-PSPConfiguration #options
Set-PSPConfiguration -Configuration $Config -Registry
```

### Get-PSPConfiguration

To return the current Protect configuration, use `Get-PSPConfiguration`. You will receive a configuration object or null if no configuration is installed. 

```text
Get-PSPConfiguration

Rules         Actions
-----         -------
{Web Request} {File, Block}

```

### Test-PSPConfiguration

To test a configuration file before installing it, you can use `Test-PSPConfiguration`. This cmdlet will use the specified configuration file and evaluate the provided script block. The `Test-PSPConfiguration` cmdlet will return either `Ok` if the script will not be blocked and `AdminBlock` if the script will be blocked. Other actions, such as TCP or HTTP, will also be executed. 

```text
Test-PSPConfiguration -ConfigurationPath ".\config.xml" -ScriptBlock { Invoke-WebRequest }
AdminBlock
```

### Save-PSPConfiguration

This cmdlet is used to save configuration files to disk. Specify the Configuration object and path.

```text
$Config = New-PSPConfiguration #options
Save-PSPConfiguration -Configuration $Config -Path .\myconfig.xml
```

## ProgramData File

You can create an XML file in `%ProgramData%\PowerShellProtect\config.xml` . You will need to set the proper permissions so the XML file is readonly. Any changes made to the XML file will automatically be reloaded by PowerShell Protect. 

## Registry 

### Registry Configuration File

You can create an XML document and store it in the registry key `HKLM\Software\Ironman Software\PowerShell Protect` in the value `Configuration`. 

### Registry Configuration Path

You can also specify the path to an XML document by creating the registry key `HKLM\Software\Ironman Software\PowerShell Protect` and setting the value `ConfigurationFile` . This needs to be the full path to the file. Environment variables will be expanded. 

## Precedence 

Configuration methods are loaded by precedence. Options higher in the precedence will be checked first. If a configuration file exists in that location, it will be loaded first and the subsequent locations will not be loaded. 

1. Registry Configuration File
2. Registry Configuration Path
3. ProgramData File

