## Upgrading a PowerShell Project to use June Release MSBuild Tasks

With the June release, MSBuild integration was included with the PowerShell project system. You can now run pre and post build PowerShell scripts that take advantage of MSBuild properties. To upgrade an existing PowerShell project to use the new MSBuild tasks, include the following line at the end of your PSPROJ file.

```
<
Import Project="$(MSBuildExtensionsPath)\PowerShell Tools for Visual Studio\PowerShellTools.targets" Condition="Exists('$(MSBuildExtensionsPath)\PowerShell Tools for Visual Studio\PowerShellTools.targets')" /
>
```

The tag should appear right before the final &lt;/Project&gt; tag.

