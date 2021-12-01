# Actions



Actions are taken after particular rules' conditions are met. Actions are specified with the `New-PSPAction` cmdlet.&#x20;

```powershell
New-PSPAction -File -Path %temp%\test.txt -Format '{appname},{rule}' -Name 'File'
```

## Action Types

### Block

The block action with block users from executing scripts that match the assigned rule.&#x20;

```
New-PSPAction -Block
```

**Parameters**

| **Parameter** | Description      |
| ------------- | ---------------- |
| Block         | Enables blocking |

### File

The file action will append to a file whenever a rule's conditions are satisfied. You will need to define the path and format for the file action.&#x20;

This example logs all the PowerShell engine application names to a file.&#x20;

```powershell
New-PSPAction -File -Path "%temp%\log.txt% -Format "{applicationName}" -Name "File"
```

#### Parameters

| Parameter | Description                                                        |
| --------- | ------------------------------------------------------------------ |
| Path      | Path to the file to write to. Environment variables are supported. |
| Format    | The formatting string used for writing the message.                |
| Name      | The name of this action                                            |

### TCP

The TCP action connects to a TCP address and port to send a formatted TCP message. This is primarily used for SIEM integration. You will need to specify the hostname, port and format settings. The message is sent as an UTF8 encoded string to the address and port.&#x20;

This example sends the application name of the PowerShell engine to the machine `MYSIEM` on port `527`.

```powershell
New-PSPAction -TCP -HostName "MYSIEM" -Port 527 -Format "{applicationName}" -Name "TCP"
```

#### Parameters

| Parameter | Description                                       |
| --------- | ------------------------------------------------- |
| HostName  | The host name or address to send the message to   |
| Port      | The port to send the message to                   |
| Format    | A formatting string for the format of the message |
| Name      | The name of this action                           |

### HTTP

The HTTP action send HTTP requests to the configured URL using the specified format. The message is sent as a UTF8 encoded string.&#x20;

This example sends the application name of the PowerShell engine to an HTTP server.&#x20;

```powershell
New-PSPAction -TCP -Address "http://powershelluniversal:8080/protect" -Format "{applicationName}" -Nanme "HTTP"
```

#### Settings

| Parameter | Description                                        |
| --------- | -------------------------------------------------- |
| Address   | The URL to send the HTTP request to.               |
| Format    | A formatting string for the format of the message  |
| Name      | The name of this action.                           |

### UDP

Send UDP datagrams to a target hostname and port. You can use formatting strings. Messages are encoded in UTF8.

This example sends the application name of the PowerShell engine to the machine `MYSIEM` on port `527`.

```powershell
New-PSPAction -UDP -HostName "MYSIEM" -Port 527 -Format "{applicationName}" -Name "TCP"
```

#### Parameters

| Parameter | Description                                       |
| --------- | ------------------------------------------------- |
| HostName  | The host name or address to send the message to   |
| Port      | The port to send the message to                   |
| Format    | A formatting string for the format of the message |
| Name      | The name of this action                           |

## Formatting Strings

You can use formatting strings to configure the output of the various audit actions (File, TCP, HTTP). You can use the following properties in your format strings.&#x20;

### Properties

| Property        | Description                                                                                                               |
| --------------- | ------------------------------------------------------------------------------------------------------------------------- |
| Script          | The complete script content.                                                                                              |
| ContentPath     | The path to the script if it was executed as a by path name. This will be an empty string if executed from the terminal.  |
| ApplicationName | The name of the application that ran PowerShell. This is typically a string with the format `PowerShell_path_version`.    |
| UserName        | The username of the user that ran that command.                                                                           |
| ComputerName    | The name of the computer running the command.                                                                             |
| Administrator   | Whether the PowerShell process has administrative permissions.                                                            |
| DomainName      | The name of the user's domain running the command.                                                                        |
| Rule            | The rule that triggered the action.                                                                                       |
| TimeStamp       | The UTC time stamp of the message.                                                                                        |

### Syntax

The property name will be replaced by the value. Put the name of the property and brackets.&#x20;

```
{timestamp}, {applicationName}, {rule}
```

## Examples

#### TCP to SIEM

In this example we are logging any use of a command containing "webrequest" with a TCP request to a SIEM (such as Splunk)

```powershell
$Condition = New-PSPCondition -Property "command" -contains -Value "webrequest"
$Siem= New-PSPAction -File -Format "{applicationName},{rule},{UserName},{ComputerName},{ContentPath},{Administrator},{DomainName}" -HostName "12.34.45.67" -Port '514' -Name 'Siem'
$Rule = New-PSPRule -Name "Web Request" -Condition $Condition -Action $Siem
$Config = New-PSPConfiguration -Rule $Rule -Action -Action @($BlockAction, $FileAction)

Test-PSPConfiguration -Configuration $Config -ScriptBlock { Invoke-WebRequest "https://www.ironmansoftware.com" }
```
