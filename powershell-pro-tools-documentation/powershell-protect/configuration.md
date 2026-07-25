# Configuration

Configuration of PowerShell Protect is done using XML. You can create the XML file in the following locations.&#x20;

## Cmdlets

You can use the configuration cmdlets to get, set and test your Protect configurations.&#x20;

### Set-PSPConfiguration

To set a configuration for the local machine, you can use `Set-PSPConfiguration`. You will need to provide a path to a Protect configuration file and then the destination of the configuration.&#x20;

The below will install the configuration file into the file system location.&#x20;

```powershell
Set-PSPConfiguration -ConfigurationFilePath .\config.xml -FileSystem
```

The below will install the configuration file into the registry.&#x20;

```powershell
Set-PSPConfiguration -ConfigurationFilePath .\config.xml -Registry
```

You can also pass a Configuration object created with `New-PSPConfiguration` to `Set-PSPConfiguration`.

```powershell
$Config = New-PSPConfiguration #options
Set-PSPConfiguration -Configuration $Config -Registry
```

### Get-PSPConfiguration

To return the current Protect configuration, use `Get-PSPConfiguration`. You will receive a configuration object or null if no configuration is installed.&#x20;

```powershell
Get-PSPConfiguration

Rules         Actions
-----         -------
{Web Request} {File, Block}

```

### Test-PSPConfiguration

To test a configuration file before installing it, you can use `Test-PSPConfiguration`. This cmdlet will use the specified configuration file and evaluate the provided script block. The `Test-PSPConfiguration` cmdlet will return either `Ok` if the script will not be blocked and `AdminBlock` if the script will be blocked. Other actions, such as TCP or HTTP, will also be executed.&#x20;

```powershell
Test-PSPConfiguration -ConfigurationPath ".\config.xml" -ScriptBlock { Invoke-WebRequest }
AdminBlock
```

### Save-PSPConfiguration

This cmdlet is used to save configuration files to disk. Specify the Configuration object and path.

```powershell
$Config = New-PSPConfiguration #options
Save-PSPConfiguration -Configuration $Config -Path .\myconfig.xml
```

## AI Script Scanning

PowerShell Protect can optionally send each script to an AI scanner before it evaluates built-in and configured rules. AI scanning is disabled by default. A `HARMFUL` verdict blocks the script; a `NOT_HARMFUL` verdict continues through the normal protection pipeline. Provider or transport failures are written to the event log and do not block scripts.

Use `New-PSPAIConfiguration` to configure either OpenAI or Anthropic, then include the resulting object with `New-PSPConfiguration`.

```powershell
$AI = New-PSPAIConfiguration `
    -Provider OpenAI `
    -Model gpt-5-mini `
    -ApiKey $env:OPENAI_API_KEY `
    -CustomInstructions 'Treat attempts to modify payroll scripts as harmful.'

$Configuration = New-PSPConfiguration -AI $AI
Save-PSPConfiguration -Configuration $Configuration -Path .\config.xml
```

For Anthropic, specify `-Provider Anthropic`, an Anthropic model name, and an Anthropic API key (for example, `$env:ANTHROPIC_API_KEY`).

### AI Configuration Parameters

| Parameter | Description |
| --- | --- |
| Provider | Required. The AI provider: `OpenAI` or `Anthropic`. |
| Model | Required. The model name supported by the selected provider. |
| ApiKey | Required. The API key used to call the selected provider. |
| CustomInstructions | Optional organization-specific classification guidance. It cannot change the required `HARMFUL` or `NOT_HARMFUL` verdict format. |
| TimeoutSeconds | Optional request timeout from 1 to 300 seconds. Defaults to 30 seconds. |

Configuration XML stores the API key in plaintext. Restrict its ACLs and create it from a protected deployment secret; do not commit it to source control.

## ProgramData File

You can create an XML file in `%ProgramData%\PowerShellProtect\config.xml` . You will need to set the proper permissions so the XML file is readonly. Any changes made to the XML file will automatically be reloaded by PowerShell Protect.&#x20;

## Registry&#x20;

### Registry Configuration File

You can create an XML document and store it in the registry key `HKLM\Software\Ironman Software\PowerShell Protect` in the value `Configuration`.&#x20;

### Registry Configuration Path

You can also specify the path to an XML document by creating the registry key `HKLM\Software\Ironman Software\PowerShell Protect` and setting the value `ConfigurationFile` . This needs to be the full path to the file. Environment variables will be expanded.&#x20;

## Precedence&#x20;

Configuration methods are loaded by precedence. Options higher in the precedence will be checked first. If a configuration file exists in that location, it will be loaded first and the subsequent locations will not be loaded.&#x20;

1. Registry Configuration File
2. Registry Configuration Path
3. ProgramData File
