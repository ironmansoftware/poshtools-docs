## PSPack.exe

PSPack.exe is the same executable used to package PowerShell scripts into .NET executables in Visual Studio. PSPack.exe accepts a script and outputs an executable or a bundled script. PSPack.exe does not require Visual Studio.

You can download PSPack.exe as part of the [PoshProTools command line tools](https://www.powershellgallery.com/packages/PowerShellProTools). PSPack is also available as a cmdlet: [Merge-Script](https://poshtools.com/docs/posh-pro-tools/merge-script/).

### Command Line Reference

**–Script**– Relative or absolute path to the script to package.

**–Output**– Relative or absolute directory to output the packaged executable.

**–License**– Installs a PoshProTools license.

**–Bundle**– Bundles dotsourced scripts with the script specified with the Script parameter. This operation is recursive, thus if a dot sourced script dot sources another script, that script will also be included.

**–Package**– Packages the script as an executable. Can be combined with Bundle and Obfuscate.

**–Obfuscate**– Obfuscates packaged executables and PowerShell script. Requires –Package.

**–Help**– Displays help information.

### Technical Considerations

Packaging Requires .NET Core SDK version 1.0.0 or higher.

Resulting executables can be run on machines running PowerShell v3 or greater.

Resulting executables run under the .NET 4.6.2 framework.

