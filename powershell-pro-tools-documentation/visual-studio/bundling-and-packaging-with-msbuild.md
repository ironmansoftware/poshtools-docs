# Packaging in Visual Studio

{% hint style="info" %}
Requires [PowerShell Pro Tools](https://ironmansoftware.com/poshtools)
{% endhint %}

PowerShell Pro Tools exposes bundling and packaging as an MSBuild task and PowerShell project system property page.

## About Packaging

Packaging a PowerShell script embeds the scrip in a .NET executable so that other users cannot modify the contexts of the script. When the executable is launched, the script will be executed just as it was from the command line. The script can still accept arguments, you can package Windows Forms applications and embed dependent modules.

### Configuring Packaging&#x20;

Packaging is configured via the PowerShell Project properties page of either a module or script project in Visual Studio. You can configure many types of options for your package.&#x20;

![Packaging settings for a PowerShell Project](<../../.gitbook/assets/image (25).png>)

#### Entry Point&#x20;

The entry point is the script that will be executed when you start your executable. This script can include other scripts or modules and enabling the bundling feature will include them as well.&#x20;

#### Bundle

Enabling the bundling feature will automatically include scripts that are dot source with the entry point script. This setting is recursive. For example, if you have a root.ps1 that dot sources a child\_level\_1.ps1 script with then references a child\_level\_2.ps1 script, all the scripts will be included together.&#x20;

#### Package as Executable

You can bundle without packaging as an executable by unchecking the Package as executable checkbox.&#x20;

#### Obfuscate executable

While you cannot open an executable in a text editor such as VS Code or Notepad, you can use a tool like dotPeek or .NET Reflector to disassemble the executable and look at the source code. Using the Obfuscate executable option, the contents of the executable will be scrambled. The executable will work the same but will be much harder to determine what is going on in the script. It prevents the casual reverse engineer from figuring out what is going on.&#x20;

#### Hide Console Window&#x20;

You can chose to hide the console window. This is especially nice when you are packaging a Windows Forms script. It will hide the PowerShell console and only show the form. You may see a brief flash of a console when starting your packaged executable with this option selected.&#x20;

#### .NET Framework Version

This is the target .NET Framework version to target for your executable. You should have the .NET Developer Pack installed for that version of the framework to successfully compile your executable. The end-user's machine will need this version of .NET (or later) installed on their machine to run your executable.&#x20;

It's recommended to use at least .NET 4.6.2.&#x20;

#### Package Modules

Selecting this option will package modules into the executable. Modules are zipped and embedded into the package. When the executable is run, they are extracted to a temporary location for the executable script to access.&#x20;

#### File Description

Sets the file description on the executable in the Details tab when viewing the properties of the executable.&#x20;

#### File Version&#x20;

Sets the file version on the executable in the Details tab when viewing the properties of the executable.&#x20;

#### Product Name

Sets the product name on the executable in the Details tab when viewing the properties of the executable.&#x20;

#### Product Version

Sets the product version on the executable in the Details tab when viewing the properties of the executable.&#x20;

#### Icon

Sets the icon for the executable.&#x20;

#### Require Elevation

Forces the user to run the executable as administrator when starting the executable. This is helpful when the script needs to access administrative resources on a machine.&#x20;

### Executing Packaging

After configuring packaging, you can execute the package process when building the project you configured. You can do this by right clicking on the project and selecting Build or by click Build and then Build Solution in the main Visual Studio Menu.&#x20;

Output from the packaging process will be shown in the Output pane.&#x20;

### Package Output&#x20;

The package is output to the configured output directory in the PowerShell Project. You can get the full path to the executable by looking in the Output pane after packaging.&#x20;

## Packaging PowerShell 7 in Visual Studio&#x20;

In Visual Studio, you can package PowerShell 7 into the executable. When you package for PowerShell 7, it includes the .NET Core runtime and PowerShell SDK directly into your executable. Your executable will be significantly larger in size but will also be able to run without having to install PowerShell 7.

{% hint style="info" %}
You will need the [.NET Core 3.1 or later](https://dotnet.microsoft.com/download/dotnet-core/thank-you/sdk-3.1.404-windows-x64-installer) SDK installed to bundle PowerShell 7 executables.&#x20;
{% endhint %}

To bundle for PowerShell 7, you will need to set two settings. First, set the .NET version to `netcoreapp31`. This will use the .NET Core 3.1 SDK to bundle your executable. Next, you will need to set the PowerShell version to 7.0 or later.&#x20;

![](<../../.gitbook/assets/image (39).png>)

The resulting executable will be written to the output directory listed in the Output pane.&#x20;

![](<../../.gitbook/assets/image (38).png>)

To deploy your executable, you will only need to include the exe file. For example:&#x20;

```
 C:\Users\adamr\source\repos\PowerShellProject3\PowerShellProject3\bin\Debug\Form.exe
```

## Packaging Resources&#x20;

Packaging resources, such as images, can be helpful when creating UI's like WPF windows. You can follow the below steps to embed resources.

First, add the resource to your PowerShell Project. Right click on your project and then click Add \ Existing Item. When the file browser dialog opens, select your resource.&#x20;

Next, right click on your resource and select properties. In the property dialog, change the Resource property to true. This will embed the resource into the assembly.&#x20;

![](<../../.gitbook/assets/image (71).png>)

Finally, if you are using WPF, then you can reference the assembly by name.&#x20;

```
<Window x:Class="WpfApp1.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:WpfApp1"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <Grid>
        <Image Source="image.png" />
    </Grid>
</Window>
```





