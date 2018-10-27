# Script Analysis

PowerShell Tools for Visual studio supports [PSScriptAnalyzer](https://github.com/PowerShell/PSScriptAnalyzer) integration. If you have PSScriptAnalyzer installed in your $PSModulePath, PoshTools will automatically call Invoke-ScriptAnalyzer on your script and show the results as tagged regions within your code. 

![Script Analyzer Alias Warning](../.gitbook/assets/image%20%282%29.png)

If you don't want PoshTools to use PSScriptAnalyzer, you can disable the analysis via the PoshTools options. Open the options menu by clicking Tools-&gt;Options and selecting PowerShell Tools. You can set Script Analyzer to false to prevent PoshTools from running PSScriptAnalyzer on your scripts. 

![Script Analyzer option](../.gitbook/assets/image%20%281%29.png)

