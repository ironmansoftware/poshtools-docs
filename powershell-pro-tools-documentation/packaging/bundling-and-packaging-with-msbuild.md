## Bundling and Packaging with MSBuild

PowerShell Pro Tools exposes bundling and packaging as an MSBuild task and PowerShell project system property page.

![](https://i0.wp.com/poshtools.com/wp-content/uploads/2017/06/packaging-1.png?resize=544%2C472&ssl=1)

You can configure bundling and packaging by changing the options available in the Advanced tab of the PowerShell project system. The entry point selects the top level script to bundle. Bundle specifies whether to combine dot sourced scripts into a merged script. If you select bundling without packaging an single PS1 file will be output to the $\(OutDir\). If you select packaging, an executable wrapping the script will be output to the $\(OutDir\). The output pane will contain all information about the bundling and packaging process.

The .NET Core SDK is required for packaging.

**Note**: You will need to[upgrade existing projects](https://poshtools.com/docs/poshtools-docs/upgrading-powershell-project-use-june-release-msbuild-tasks/)to take advantage of the PowerShell Tools MSBuild targets. Visual Studio 2015 requires[manual steps](https://poshtools.com/docs/poshtools-docs/enabling-msbuild-support-visual-studio-2015-powershell-projects/)to enable MSBuild targets.

