# Script Analysis and Quick Fix

## PSScript Analyzer Integration

PowerShell Tools for Visual studio supports [PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer) integration. If you have PSScriptAnalyzer installed in your $PSModulePath, PoshTools will automatically call Invoke-ScriptAnalyzer on your script and show the results as tagged regions within your code. 

![Script Analyzer Alias Warning](../.gitbook/assets/image%20%284%29.png)

## Quick Fix

PoshTools supports quick fix actions provided by PSScriptAnalyzer. If the suggestion has a Suggested Correction, PoshTools will provide a Quick Action light bulb next to the line that needs to be addressed. 

![Executing quick fix actions](../.gitbook/assets/quickfix.gif)

## Configuration

If you don't want PoshTools to use PSScriptAnalyzer, you can disable the analysis via the PoshTools options. Open the options menu by clicking Tools-&gt;Options and selecting PowerShell Tools. You can set Script Analyzer to false to prevent PoshTools from running PSScriptAnalyzer on your scripts. 

You can also customize the Script Analyzer Setting. This can be either a[ built in setting or a PSSA setting file. ](https://github.com/PowerShell/PSScriptAnalyzer#settings-support-in-scriptanalyzer)

![Setting in the options menu](../.gitbook/assets/image%20%281%29.png)

