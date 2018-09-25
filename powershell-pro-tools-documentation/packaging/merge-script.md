## Merge-Script

Merge-Script is part of the command line utilities [PowerShell module for PowerShell Pro Tools](https://www.powershellgallery.com/packages/PowerShellProTools). Merge-Script calls pspack.exe to produce bundle scripts or packaged executables.  
**NAME**  
Merge-Script

**SYNOPSIS**  
Packages scripts into an executable or single PS1 script.

**SYNTAX**  
Merge-Script -Script &lt;String&gt; \[-OutputPath &lt;String&gt;\] \[-Package &lt;SwitchParameter&gt;\] \[-Bundle &lt;SwitchParameter&gt;\] \[-Obfuscate &lt;SwitchParameter&gt;\]  
\[&lt;CommonParameters&gt;\]

**DESCRIPTION**  
Packages scripts into an executable or single PS1 script. Specify the root script to package to produce a .NET  
executable that hosts the script. You can choose to bundle dot sourced scripts automatically using the Bundle  
switch. You can also bundle multiple PS1s into a single PS1 by using Bundle without Package. Use the Obfuscate parameter to obfuscate .NET assemblies.

**PARAMETERS**  
-Script &lt;String&gt;  
The root script to package.

Required? true  
Position? named  
Default value  
Accept pipeline input? false  
Accept wildcard characters? false

-OutputPath \[&lt;String&gt;\]  
The directory to output scripts or executables from this command.

Required? false  
Position? named  
Default value  
Accept pipeline input? false  
Accept wildcard characters? false

-Package \[&lt;SwitchParameter&gt;\]  
Whether or not to package the script as a .NET executable.

Required? false  
Position? named  
Default value  
Accept pipeline input? false  
Accept wildcard characters? false

-Bundle \[&lt;SwitchParameter&gt;\]  
Whether or not to bundle dot sourced scripts. If this switch is specified, the bundler will try and locate dot  
sourced scripts and include them with the package. This operation is recursive. Bundling can locate scripts  
relative to the root script and can expand the $PSScriptRoot variable.

Required? false  
Position? named  
Default value  
Accept pipeline input? false  
Accept wildcard characters? false

-Obfuscate \[&lt;SwitchParameter&gt;\]  
Whether or not to obfuscate the .NET assembly.

Required? false  
Position? named  
Default value  
Accept pipeline input? false  
Accept wildcard characters? false

&lt;CommonParameters&gt;  
This cmdlet supports the common parameters: Verbose, Debug,  
ErrorAction, ErrorVariable, WarningAction, WarningVariable,  
OutBuffer, PipelineVariable, and OutVariable. For more information, see  
about\_CommonParameters \(http://go.microsoft.com/fwlink/?LinkID=113216\).

**INPUTS**  
None

**OUTPUTS**  
System.Object

**EXAMPLE 1**

Package a script into an executable

```
C:\PS> Merge-Script -Script .\MyScript.ps1
```

Outputs an executable, .\MyScript.exe, to the same location as the specified script.  
**EXAMPLE 2**

Packages a script and outputs it to the specified path.

```
C:\PS> Merge-Script -Script .\MyScript.ps1 -OutputPath .\outDir
```

Packages a script and outputs it to the specified path.  
**EXAMPLE 3**

Bundles and packages a script and its dependencies into an executable.

```
C:\PS> Merge-Script -Script .\MyScript.ps1 -OutputPath .\outDir -Bundle
```

Merge-Script searches for dot sourced files in the MyScript.ps1 file and includes them with the package. This  
operation is recusive, thus if a dot sourced script dot sources another script, that script will also be included.  
**EXAMPLE 4**

Bundles a script as a single PS1

```
C:\PS> Merge-Script -Script .\MyScript.ps1 -OutputPath .\outDir -Bundle -Package
```

Merge-Script searches for dot sourced files in the MyScript.ps1 file and includes them with the package. This  
operation is recusive, thus if a dot sourced script dot sources another script, that script will also be included.  
Specifying Script as the OutputType produces a PS1 file rather than an executable.

