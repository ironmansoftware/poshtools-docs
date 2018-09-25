## Code Conversion

PowerShell Pro Tools can convert between C\# and PowerShell code. The conversion success rate depends on the language syntax used by both languages. For example, PowerShell does not support generics or async\await and C\# does not support cmdlets. Some conversions are accomplished using code that mimics the intent but not the exact code structure. For example, using the Get-Process cmdlet in C\# would require the use of the PowerShell.Create method and an invocation into the PowerShell engine. Instead, PowerShell Pro Tools converts the Get-Process call into the corresponding Process.GetProcessesByName or Process.GetProcessesById method calls in C\#.

**Invoking Conversion**

Conversion is accomplished by copying the source code to the clipboard and using either the Paste as PowerShell or Paste as C\# commands in the target source file. You can right click within the target source file to access this option.

**Examples**

**Converting PowerShell to C\# directly.**

In the example video, PowerShell is converted directly to C\# code using classes in .NET rather than the cmdlet that was in the script.



**Converting PowerShell to C\# by using the System.Management.Automation classes. **

In this example, PowerShell is converted to C\# by using the System.Management.Automation classes to execute the PowerShell cmdlet in the PowerShell engine hosted in C\#.



**Converting C\# to PowerShell**

Converts C\# to PowerShell by converting all the C\# syntax to PowerShell syntax.



**Converting C\# P\Invoke Signatures to PowerShell Script**

  


