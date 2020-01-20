# Bundling and Packaging with MSBuild

{% hint style="info" %}
Requires [PowerShell Pro Tools](https://ironmansoftware.com/poshtools)
{% endhint %}

PowerShell Pro Tools exposes bundling and packaging as an MSBuild task and PowerShell project system property page.

## About Packaging

Packaging a PowerShell script embeds the scrip in a .NET executable so that other users cannot modify the contexts of the script. When the executable is launched, the script will be executed just as it was from the command line. The script can still accept arguments, you can package Windows Forms applications and embed dependent modules.

### Configuring Packaging 

Packaging is configured via the PowerShell Project properties page of either a module or script project in Visual Studio. You can configure many types of options for your package. 

![Packaging settings for a PowerShell Project](../../../.gitbook/assets/image.png)

#### Entry Point 

The entry point is the script that will be executed when you start your executable. This script can include other scripts or modules and enabling the bundling feature will include them as well. 

#### Bundle

Enabling the bundling feature will automatically include scripts that are dot source with the entry point script. This setting is recursive. For example, if you have a root.ps1 that dot sources a child\_level\_1.ps1 script with then references a child\_level\_2.ps1 script, all the scripts will be included together. 

#### Package as Executable

You can bundle without packaging as an executable by unchecking the Package as executable checkbox. 

#### Obfuscate executable

While you cannot open an executable in a text editor such as VS Code or Notepad, you can use a tool like dotPeek or .NET Reflector to disassemble the executable and look at the source code. Using the Obfuscate executable option, the contents of the executable will be scrambled. The executable will work the same but will be much harder to determine what is going on in the script. It prevents the casual reverse engineer from figuring out what is going on. 

#### Hide Console Window 

You can chose to hide the console window. This is especially nice when you are packaging a Windows Forms script. It will hide the PowerShell console and only show the form. You may see a brief flash of a console when starting your packaged executable with this option selected. 

#### .NET Framework Version

This is the target .NET Framework version to target for your executable. You should have the .NET Developer Pack installed for that version of the framework to successfully compile your executable. The end-user's machine will need this version of .NET \(or later\) installed on their machine to run your executable. 

It's recommended to use at least .NET 4.6.2. 

#### Package Modules

Selecting this option will package modules into the executable. Modules are zipped and embedded into the package. When the executable is run, they are extracted to a temporary location for the executable script to access. 

#### File Description

Sets the file description on the executable in the Details tab when viewing the properties of the executable. 

#### File Version 

Sets the file version on the executable in the Details tab when viewing the properties of the executable. 

#### Product Name

Sets the product name on the executable in the Details tab when viewing the properties of the executable. 

#### Product Version

Sets the product version on the executable in the Details tab when viewing the properties of the executable. 

#### Icon

Sets the icon for the executable. 

#### Require Elevation

Forces the user to run the executable as administrator when starting the executable. This is helpful when the script needs to access administrative resources on a machine. 

### Executing Packaging

After configuring packaging, you can execute the package process when building the project you configured. You can do this by right clicking on the project and selecting Build or by click Build and then Build Solution in the main Visual Studio Menu. 

Output from the packaging process will be shown in the Output pane. 

### Package Output 

The package is output to the configured output directory in the PowerShell Project. You can get the full path to the executable by looking in the Output pane after packaging. 

