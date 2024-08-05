---
description: Setup packaging within a continuous integration environment.
---

# Continuous Integration

## MSBuild and Azure DevOps

You will need to include the MSBuild targets and assemblies in your repository in order to packaging during the build process.&#x20;

### Add Assets to Repository&#x20;

The MSBuild assets are stored in the Visual Studio MSBuild directory when the extension is installed.&#x20;

```
C:\Program Files\Microsoft Visual Studio\2022\Enterprise\PowerShell Tools for Visual Studio
```

Your path to this folder may different based on your version and edition of Visual Studio. [VSWhere ](https://github.com/microsoft/vswhere)can be used to determine this file location.&#x20;

Place the files in a directory that you can link to during the build process. As an example, you can place them at the root of the repo.&#x20;

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption><p>PowerShell Tools for VS Folder</p></figcaption></figure>

### Update PSSProj File&#x20;

Next, update the PSSProj file to import the targets file for PowerShell Tools for Visual Studio. Include a condition so the build still works locally. This should be placed at the bottom of the file after the existing import. If you placed the assets in a different location, you will need to update your path. The below example uses the SolutionDir MSBuild property to locate the directory of the solution file.&#x20;

```markup
<!-- Existing:  <Import Project="$(MSBuildExtensionsPath)\PowerShell Tools for Visual Studio\PowerShellTools.targets" Condition="Exists('$(MSBuildExtensionsPath)\PowerShell Tools for Visual Studio\PowerShellTools.targets')" /> -->
<Import Project="$(SolutionDir)\PowerShell Tools for Visual Studio\PowerShellTools.targets" Condition="Exists('$(SolutionDir)\PowerShell Tools for Visual Studio\PowerShellTools.targets')" />
```

### Setup the Azure DevOps Pipeline

Finally, setup the Azure DevOps pipeline to run the `VSBuild` target against the Solution Directory. This example uploads the compiled artifact after the build so it can be downloaded from the Azure DevOps portal.

```yaml
trigger:
- main

pool:
  vmImage: windows-latest

steps:
- task: VSBuild@1
  inputs:
    solution: '**\*.sln'
- publish: $(System.DefaultWorkingDirectory)/bin/Debug
  artifact: App
```
