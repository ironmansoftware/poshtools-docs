# Packaging

## Requirements:

* [.NET Core 3.1 SDK or Later](https://dotnet.microsoft.com/download/dotnet/thank-you/sdk-3.1.415-windows-x64-installer)
* [.NET 5.0 SDK for Packaging PowerShell 7.1](https://dotnet.microsoft.com/download/dotnet/thank-you/sdk-5.0.403-windows-x64-installer)
* .[NET 4.6.2 Developer Pack](https://www.microsoft.com/en-us/download/details.aspx?id=53321)
* Internet Connection

The packaging component of PowerShell Pro Tools allows you to bundle, package as an executable and obfuscate the resulting executable.

## Bundling

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

You can bundle scripts with PowerShell Pro tools using [Visual Studio](https://poshtools.com/docs/posh-pro-tools/bundling-packaging-msbuild/) or [Merge-Script](https://poshtools.com/docs/posh-pro-tools/merge-script/).

## Packaging as an Executable

Scripts can be packaged as a .NET executable for easy deployment on any Windows system. You can combine bundling with packaging to include multiple scripts into a single executable.

You can package scripts with PowerShell Pro tools using [Visual Studio](https://poshtools.com/docs/posh-pro-tools/bundling-packaging-msbuild/) or [Merge-Script](https://poshtools.com/docs/posh-pro-tools/merge-script/).

## Obfuscation

Once scripts have been packaged as a .NET executable, you can take an additional step and obfuscate the executable. This will make it much more difficult for users to decompile your executable and inspect your PowerShell script. Obfuscated assemblies scramble the C# code as well as the PowerShell script.

{% hint style="warning" %}
Obfuscation is not supported when packaging PowerShell 7.
{% endhint %}

You can obfuscate executables with PowerShell Pro tools using Visual Studio, Visual Studio Code and Merge-Script.

## Anti-Virus

Anti-Virus vendors may flag executables as malicious after they have been compiled. You can use [VirusTotal](https://www.virustotal.com/gui/) to verify which vendors may flag your executable. If you need to submit a executable for evaluation, you can use the below list of vendor verification processes. &#x20;

* [Microsoft Defender](https://www.microsoft.com/en-us/wdsi/filesubmission)&#x20;

Learn more about issues with [anti-virus here](anti-virus.md).&#x20;

## NuGet

We use the Microsoft NuGet.org package system to download the packages necessary to host PowerShell in .NET. You will need an internet connection to access NuGet.org.&#x20;

By default, you should have the package source defined. If you do not, you can do so with the following `dotnet` command line.&#x20;

```
dotnet nuget add source https://api.nuget.org/v3/index.json -n nuget.org
```

For offline builds, you can also host your [own NuGet feed](https://docs.microsoft.com/en-us/nuget/hosting-packages/overview).&#x20;
