## Getting started with Packaging

**Requirements:**

* [.NET Core 1.0+](https://github.com/dotnet/core/releases)
* .[NET 4.6.2 Developer Pack](https://www.microsoft.com/en-us/download/details.aspx?id=53321)

The packaging component of PowerShell Pro Tools allows you to bundle, package as an executable and obfuscate the resulting executable.

**Bundling**

The process of bundling takes multiple scripts and creates a single script. Bundling automatically follows dot sourced scripts and includes them in the final output script. This process is recursive and will include scripts that are included by other scripts. Take for example you have three scripts. The first script looks like this.

`Write-Host "Hi! I'm script 1"`

`. $PSScriptRoot\Script2.ps1`

Script1.ps1 outputs “Hi! I’m script 1” and then calls Script2.ps1 found at the $PSScriptRoot. Script2.ps1 could then look like this.

\`Write-Host "Hi! I'm script 2"

.\Script3.ps1\`

Script2.ps2 outputs “Hi! I’m script 2” and the calls Script3.ps1. Script3.ps1 could consist of something like this.

`Write-Host "Hi! I'm script 3"`

If you wanted to deploy these scripts to an environment, you’d need to make sure to copy each script. Using bundling, you could combine the scripts, automatically, into a single script. The resulting script would look like this.

\`Write-Host "Hi! I'm script 1"

Write-Host "Hi! I'm script 2"

Write-Host "Hi! I'm script 3"\`

This enables developers to organize their code into multiple scripts but then deploy a single script. You could store all three scripts in source control, such as GitHub, and then run a bundling step using a continuous integration system, such as AppVeyor.

You can bundle scripts with PowerShell Pro tools using [Visual Studio](https://poshtools.com/docs/posh-pro-tools/bundling-packaging-msbuild/), [PSPack.exe](https://poshtools.com/docs/posh-pro-tools/pspack-exe/) or [Merge-Script](https://poshtools.com/docs/posh-pro-tools/merge-script/).

**Packaging as an Executable**

Scripts can be packaged as a .NET executable for easy deployment on any Windows system. You can combine bundling with packaging to include multiple scripts into a single executable.

You can package scripts with PowerShell Pro tools using [Visual Studio](https://poshtools.com/docs/posh-pro-tools/bundling-packaging-msbuild/), [PSPack.exe](https://poshtools.com/docs/posh-pro-tools/pspack-exe/) or [Merge-Script](https://poshtools.com/docs/posh-pro-tools/merge-script/).

**Obfuscation**

Once scripts have been packaged as a .NET executable, you can take an additional step and obfuscate the executable. This will make it much more difficult for users to decompile your executable and inspect your PowerShell script. Obfuscated assemblies scramble the C\# code as well as the PowerShell script.

![](https://i2.wp.com/poshtools.com/wp-content/uploads/2017/06/2017-06-28_11-06-46.png?resize=1024%2C441&ssl=1)

You can obfuscate executables with PowerShell Pro tools using [Visual Studio](https://poshtools.com/docs/posh-pro-tools/bundling-packaging-msbuild/), [PSPack.exe](https://poshtools.com/docs/posh-pro-tools/pspack-exe/) or [Merge-Script](https://poshtools.com/docs/posh-pro-tools/merge-script/).

