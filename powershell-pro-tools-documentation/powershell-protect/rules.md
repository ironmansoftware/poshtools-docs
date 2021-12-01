---
description: Rules for PowerShell Protect.
---

# Rules

You can configure rules to determine which script executions to audit and\or block. This document outlines how to configure rules. You can generate rules with the configuration cmdlets.&#x20;

```powershell
$Condition = New-PSPCondition -Property "command" -contains -Value "webrequest"
$BlockAction = New-PSPAction -Block
$FileAction = New-PSPAction -File -Format "{applicationName},{rule}" -Path "%temp%\audit.csv" -Name 'File'
$Rule = New-PSPRule -Name "Web Request" -Condition $Condition -Action @($BlockAction, $FileAction)
```

## Conditions

Rules are evaluated based on conditions. Conditions look at various properties of a PowerShell script and execution environment to determine whether the script can run or if it should be audited.&#x20;

### Multiple Conditions

Rules can contain multiple conditions. If all of the conditions are met, the rule will execute the actions defined by the action references.&#x20;

```powershell
$Condition = New-PSPCondition -Property "command" -contains -Value "webrequest"
$Condition2 = New-PSPCondition -Property "command" -contains -Value "invoke"
$BlockAction = New-PSPAction -Block
$Rule = New-PSPRule -Name "Web Request" -Condition @($Condition, $Condition1) -Action @($BlockAction, $FileAction)
```

### Properties

Conditions check specific properties to ensure that they meet the given criteria. Below is a list of the available properties. PowerShell Protect takes advantage of the PowerShell Abstract Syntax Tree (AST) to analyzer scripts.

| Property Name    | Description                                                                                                                                                                                                                                       |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Administrator    | The administrator property returns true if the current user is an elevated user. This property validates not only that the user has admin privileges but that they also are running a UAC elevated application.                                   |
| ApplicationName  | The application property returns a string that contains information about the application running PowerShell. This may be a process like PowerShell.exe or Pwsh.exe. This could also be a third-party application running the PowerShell engine.  |
| Command          | The command property matches commands. PowerShell Protect uses the script's AST to match command executions within a script. Using the command property condition won't match definitions of commands but only executions.                        |
| ComputerName     | The computer name property matches the current computer's name.                                                                                                                                                                                   |
| ContentPath      | The content path property matches the path of the script that was run. This will be a null string when running a command inside a terminal like PowerShell.exe.                                                                                   |
| Domain           | The domain path property returns the current domain of the user running the command.                                                                                                                                                              |
| DomainController | The domain controller property returns true if the current machine is a domain controller.                                                                                                                                                        |
| Member           | The member property matches any .NET property or methods that are executed within the script. This can be helpful for blocking method calls to .NET classes that may invoke low-level APIs that may be undesirable.                               |
| Script           | The script property returns a string that contains the entire content of the script. You can use this for using basic matching of strings within the script.                                                                                      |
| String           | The string property matches strings within the script. This includes both regular strings and strings that contain variable expansions.                                                                                                           |
| Variable         | The variable property matches variables within the script.                                                                                                                                                                                        |

### Operators

Operators are used for matching properties to values. Below is a list of available operators. None of the operators are case sensitive.&#x20;

| Operator      | Description                                                                         |
| ------------- | ----------------------------------------------------------------------------------- |
| Contains      | Contains determines whether a property contains the value string.                   |
| NotContains   | NotContains determines whether a property doesn't contain the value string.         |
| EndsWith      | EndsWith determines whether a property ends with the value string.                  |
| NotEndsWith   | NotEndsWith determines whether a property doesn't end with the value string.        |
| Equals        | Equals determines the property equals the value string.                             |
| NotEquals     | NotEquals determines whether the property doesn't equal the value string.           |
| StartsWith    | StartsWith determines whether the property starts with the value string.            |
| NotStartsWith | NotStartsWith determines whether the property doesn't start with the value string.  |
| Matches       | Matches uses RegEx to determine whether the property matches the value string.      |

### Value

The value is a string to match with the property value during execution. This is a string, boolean or a RegEx.&#x20;

## Default Rules

The default rules are built-in to PowerShell Protect and do not require configuration.&#x20;

#### AMSI Bypass Protection <a href="#amsi-bypass-protection" id="amsi-bypass-protection"></a>

The AMSI bypass protection will be enabled by default. An AMSI bypass prevents AMSI from loading and thus prevents Windows Defender from scanning scripts as well as PowerShell Protect.&#x20;

&#x20;You can learn more about AMSI bypass by reading our [previous post](https://blog.ironmansoftware.com/protect-amsi-bypass).

#### Module and Script Block Logging Bypass Protection <a href="#module-and-script-block-logging-bypass-protection" id="module-and-script-block-logging-bypass-protection"></a>

Module and script block logging provide insight into the scripts that are running on a system. There are techniques to bypass this logging and Protect will block those by default.&#x20;

#### Assembly Load from Memory <a href="#assembly-load-from-memory" id="assembly-load-from-memory"></a>

One common technique for loading malicious assemblies in a fileless attack is to store the assembly as a base64 encoded string within the script. The `System.Reflection.Assembly.Load` method will be used to load the byte array directly in memory without accessing the file system. PowerShell Protect will now detect the use of this method and block the script.

Here is a [blog post](https://0x00-0x00.github.io/research/2018/10/28/How-to-bypass-AMSI-and-Execute-ANY-malicious-powershell-code.html) about an AMSI bypass loaded with this method.

An example of this in action from the blog post is listed below.

```powershell
function Bypass-AMSI
{
    if(-not ([System.Management.Automation.PSTypeName]"Bypass.AMSI").Type) {
        [Reflection.Assembly]::Load([Convert]::FromBase64String("truncated")) | Out-Null
        Write-Output "DLL has been reflected";
    }
    [Bypass.AMSI]::Disable()
}
```

#### Disabling Defender <a href="#disabling-defender" id="disabling-defender"></a>

Windows comes with cmdlets for managing the local Windows Defender instance. The `Set-MpPreference` cmdlet can be used to disable Windows Defender by using the `DisableRealtimeMonitoring` parameter. Although you will need administrative permissions to perform this action, you will be able to see if users are attempting to execute this command and further investigate the behavior.

An example of the command that is blocked is listed below.

```powershell
Set-MpPreference -DisableRealtimeMonitoring $true
```

#### Invoke-Expression <a href="#use-of-the-systemreflectionemit-namespace" id="use-of-the-systemreflectionemit-namespace"></a>

`Invoke-Expression` is used to execute arbitrary strings as PowerShell script. While it can be used for legitimate purposes, it is often used to download and execute malicious payloads such as this recently discovered [exploit](https://blog.huntresslabs.com/hiding-in-plain-sight-part-2-dfec817c036f).

#### Use of the System.Reflection.Emit Namespace <a href="#use-of-the-systemreflectionemit-namespace" id="use-of-the-systemreflectionemit-namespace"></a>

One common technique used by fileless attacks is the ability to define .NET assemblies and types in memory. This can be done with the `System.Reflection.Emit` namespace. Rather than invoking the C# compiler, like with `Add-Type`, you won’t see any file system activity when this type of attack is taking place. PowerShell Protect will now watch for these types of method calls, audit and block them.

You can see an example of this in [PowerSploit’s](https://github.com/PowerShellMafia/PowerSploit/blob/master/CodeExecution/Invoke-ReflectivePEInjection.ps1) `Invoke-ReflectivePEInjection` command for loading binaries into memory without file system access.

This is one way of loading a binary, like Mimikatz, into memory from a script-based payload.

An example of the script that would be blocked.

```powershell
$Domain = [AppDomain]::CurrentDomain
$DynamicAssembly = New-Object System.Reflection.AssemblyName('DynamicAssembly')
$AssemblyBuilder = $Domain.DefineDynamicAssembly($DynamicAssembly, [System.Reflection.Emit.AssemblyBuilderAccess]::Run)
$ModuleBuilder = $AssemblyBuilder.DefineDynamicModule('DynamicModule', $false)
$ConstructorInfo = [System.Runtime.InteropServices.MarshalAsAttribute].GetConstructors()[0]
```

#### PowerSploit <a href="#powersploit" id="powersploit"></a>

Windows Defender already blocks a bunch of the PowerSploit commands. You won’t be able to use `Invoke-Mimikatz` or `Invoke-ReflectivePEInjection` as-is on a default Windows environment because Defender is checking for these commands. PowerShell Protect now checks for all functions defined in PowerSploit to ensure that no one is poking around your environment with any of the tools.

#### Marshal Class <a href="#marshal-class" id="marshal-class"></a>

The use of the `System.RuntimeServices.Interop.Marshal` class may be an indication that someone is attempting to manipulate memory within the PowerShell process. This class provides methods for allocating unmanaged memory segments, copying bytes around and determining memory sizes, among other things.

The use of the `Marshal` class is rare in the C# and the .NET world and should be even more rare in the PowerShell world. Although it may not be an actual attack, it’s a strange thing to be doing for most sysadmins.

An example of the script that would be blocked.

```powershell
[System.RuntimeServices.Interop.Marshal]::SizeOf($MyVariable)
```

#### Persistent WMI Event Subscription <a href="#persistent-wmi-event-subscription" id="persistent-wmi-event-subscription"></a>

Attackers may use WMI to create a persistent WMI event subscription to run a command during system start up or user logon. This is a [difficult attack to detect](https://github.com/PowerShellMafia/PowerSploit/blob/master/Persistence/Persistence.psm1#L18). It’s also a less common use of PowerShell. We’ve decided to block it by default in PowerShell Protect.

An example of the script that would be blocked.

````powershell
 $ElevatedTrigger = "`"```$Filter=Set-WmiInstance -Class __EventFilter -Namespace ```"root\subscription```" -Arguments @{name='Updater';EventNameSpace='root\CimV2';QueryLanguage=```"WQL```";Query=```"SELECT * FROM __InstanceModificationEvent WITHIN 60 WHERE TargetInstance ISA 'Win32_PerfFormattedData_PerfOS_System' AND TargetInstance.SystemUpTime >= 240 AND TargetInstance.SystemUpTime < 325```"};```$Consumer=Set-WmiInstance -Namespace ```"root\subscription```" -Class 'CommandLineEventConsumer' -Arguments @{ name='Updater';CommandLineTemplate=```"```$(```$Env:SystemRoot)\System32\WindowsPowerShell\v1.0\powershell.exe -NonInteractive```";RunInteractively='false'};Set-WmiInstance -Namespace ```"root\subscription```" -Class __FilterToConsumerBinding -Arguments @{Filter=```$Filter;Consumer=```$Consumer} | Out-Null`""
````

#### BloudHound Injestor Execution <a href="#bloudhound-injestor-execution" id="bloudhound-injestor-execution"></a>

[BloudHound](https://github.com/BloodHoundAD/BloodHound) is an Active Directory tool for enumerating and visualizing relationships in a domain or forest. It uses an injestor, [SharpHound](https://github.com/BloodHoundAD/SharpHound3), to execute the enumeration of objects and discover their relationships. There are some signs of SharpHound usage that we have identified and blocked to prevent people from executing SharpHound. Other rules, like Assembly Loading for Memory, will also prevent this type of script execution.

An example of the [script](https://github.com/BloodHoundAD/BloodHound/blob/master/Ingestors/SharpHound.ps1) that would be blocked.

```powershell
$EncodedCompressedFile = 'truncated'
$DeflatedStream = New-Object IO.Compression.DeflateStream([IO.MemoryStream][Convert]::FromBase64String($EncodedCompressedFile),[IO.Compression.CompressionMode]::Decompress)
$UncompressedFileBytes = New-Object Byte[](833536)
$DeflatedStream.Read($UncompressedFileBytes, 0, 833536) | Out-Null
$Assembly = [Reflection.Assembly]::Load($UncompressedFileBytes)
$BindingFlags = [Reflection.BindingFlags] "Public,Static"
$a = @()
$Assembly.GetType("Costura.AssemblyLoader", $false).GetMethod("Attach", $BindingFlags).Invoke($Null, @())
$Assembly.GetType("SharpHound3.SharpHound").GetMethod("InvokeSharpHound").Invoke($Null, @(,$passed))
```

#### Kerberoasting <a href="#kerberoasting" id="kerberoasting"></a>

Kerberoasting is a lateral movement technique that abuses the Kerberos Ticket Granting Service (TGS). Using tools like Mimikatz, tickets can be dumped from memory, brute forced offline and then used to exfiltrate passwords which can be used to move laterally across an environment.

PowerShell Protect looks for signs of this type of attack being performed based on signatures found in scripts like [Invoke-Kerberoasting.ps1](https://github.com/EmpireProject/Empire/blob/master/data/module\_source/credentials/Invoke-Kerberoast.ps1).

An example of the script that would be blocked.

```powershell
elseif ( ($_ -eq 'lastlogon') -or ($_ -eq 'lastlogontimestamp') -or ($_ -eq 'pwdlastset') -or ($_ -eq 'lastlogoff') -or ($_ -eq 'badPasswordTime') ) {
    # convert timestamps
    if ($Properties[$_][0] -is [System.MarshalByRefObject]) {
        # if we have a System.__ComObject
        $Temp = $Properties[$_][0]
        [Int32]$High = $Temp.GetType().InvokeMember('HighPart', [System.Reflection.BindingFlags]::GetProperty, $Null, $Temp, $Null)
        [Int32]$Low  = $Temp.GetType().InvokeMember('LowPart',  [System.Reflection.BindingFlags]::GetProperty, $Null, $Temp, $Null)
        $ObjectProperties[$_] = ([datetime]::FromFileTime([Int64]("0x{0:x8}{1:x8}" -f $High, $Low)))
    }
    else {
        # otherwise just a string
        $ObjectProperties[$_] = ([datetime]::FromFileTime(($Properties[$_][0])))
    }
}
```

## Disabling Default Rules

You can disable default rules by using the `-DisableBuiltinRules`.

```powershell
New-PSPConfiguration -DisableBuiltinRules
```

You can disable default rules by using the `-DisabledBuiltInConditions` parameter.&#x20;

```powershell
New-PSPConfiguration -DisabledBuiltInConditions "asmiBypass"
```
