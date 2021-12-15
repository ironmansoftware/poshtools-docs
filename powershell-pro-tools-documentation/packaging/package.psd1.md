# Package.psd1

{% hint style="info" %}
Requires [PowerShell Pro Tools](https://ironmansoftware.com/poshtools)
{% endhint %}

## About

This about file contains information about using hashtables and PSD1 files to configure Merge-Script. These psd1 files are also used by PowerShell Tools for Visual Studio Code.&#x20;

### Config File Schema

```powershell
@{
        Root = 'c:\Users\Adam\Desktop\service.ps1' # Root script to package. This is the main entry point for the package. 
        OutputPath = 'c:\Users\Adam\Desktop\out' # The output directory for the packaging process. 
        Package = @{
            Enabled = $true # Whether to package as an executable. 
            Obfuscate = $false # Whether to obfuscate the resulting executable. 
            HideConsoleWindow = $false # Whether to hide the console window.  Only valid for console applications.
            # The target .NET Framework version. You will need the .NET Developer Pack for this version installed on your machine.
            # If target PowerShell 7, you can also use netcoreapp31 here 
            DotNetVersion = 'v4.6.2'
            FileVersion = '1.0.0' # The output file version
            FileDescription = '' # The output file description
            ProductName = '' # The output file product name
            ProductVersion = '' # The output file product version.
            Copyright = '' # The output file copyright
            RequireElevation = $false # Whether to require elevation when running the executable. Only valid for console applications. 
            ApplicationIconPath = '' # The path to the application icon to use for the executable. 
            PackageType = 'Console' # The type of executable to generate. Valid values are Service or Console. 
            ServiceName = "" # The name of the service if the package type is Service. 
            ServiceDisplayName = "" # The display name of the service if the package type is Service. 
            HighDPISupport = $true  # Whether to enable high DPI support for WinForm applications
            PowerShellArguments = '' # Sets the arguments for the PowerShell process that is hosted within the executable. You can use arguments like -NoExit, -ExecutionPolicy and -NoProfile.
            Platform = 'x64' # Sets the architecture of the executable. Can be either 'x86' or 'x64'
            PowerShellVersion = 'Windows PowerShell' # You can specify Windows PowerShell or PowerShell 7 or later versions version (e.g. 7.0.0)
            RuntimeIdentifier = 'win-x64' # You can specify other runtimes like linux-x64 (See .NET Core runtime identifiers)
            DisableQuickEdit = $false # Disables the quick edit mode on windows console apps
            Resources = [string[]]@() # Resources to embed in the output executable
        }
        Bundle = @{
            Enabled = $true # Whether to bundle multiple PS1s into a single PS1. Always enabled when Package is enabled. 
            Modules = $true # Whether to bundle modules into the package
        }
    }
    
```

### Using a config file

A config file can be used either from within a PowerShell script as a hashtable or imported from a PSD1 file containing the hashtable.

## Options

### Package

Options for the packager. See the config file schema for the proper layout.&#x20;

#### Enabled&#x20;

Whether the packager is enabled. Valid values are either $true or $false.&#x20;

#### Obfuscate&#x20;

Whether to obfuscate the assembly. Only valid for Windows PowerShell. Valid values are $true or $false.&#x20;

#### HideConsoleWindow

Whether to hide the console window. Useful for when packaging form applications. Valid values are $true or $false.&#x20;

#### DotNetVersion

The .NET version to target for the executable. You can find the valid values below.&#x20;

| PowerShell Version | Valid .NET Versions                              |
| ------------------ | ------------------------------------------------ |
| Windows PowerShell | net4.6.2, net4.7.0, net4.7.1, net4.7.2, net4.8.0 |
| PowerShell 7.0.x   | netcoreapp31                                     |
| PowerShell 7.1.x   | net5.0                                           |
| PowerShell 7.2.x   | net6.0                                           |

#### FileVersion

The file version to display in the assembly properties.

#### FileDescription

The file description&#x20;

## EXAMPLES

It is not required to include all aspects of the config when using Merge-Script. The only required components are Root and OutputPath. Aside from that, anything that is not include will be considered false. This means that in the below example, packaging is disabled but bundling is not. The below operation will not bundle nested modules or required assemblies of any modules it is bundling.

```powershell
Merge-Script -Config @{ 
    Root = ".\MyScript.ps1"
    OutputPath = ".\"
    Bundle = @{
        Enabled = $true
        Modules = $true
    }
}
```

### Create console application

Creates a PowerShell console based application that has an application icon and hides the console window.&#x20;

```powershell
@{
        Root = 'c:\Users\Adam\Desktop\form.ps1'
        OutputPath = 'c:\Users\Adam\Desktop\out'
        Package = @{
            Enabled = $true
            HideConsoleWindow = $true
            DotNetVersion = 'v4.6.2'
            ApplicationIconPath = 'C:\users\adam\desktop\icon.ico'
        }
    }
    
```

### Create a service

Creates a PowerShell service based on the service.ps1 file and outputs to the out directory on the desktop. It will use the .NET 4.6.2 Developer Pack. The service name will be PSService and the display name will be PowerShell Service.&#x20;

For more information on services, see the [Package as Service](package-a-service.md) section.

```powershell
@{
        Root = 'c:\Users\Adam\Desktop\service.ps1'
        OutputPath = 'c:\Users\Adam\Desktop\out'
        Package = @{
            Enabled = $true
            DotNetVersion = 'v4.6.2'
            FileVersion = '1.0.0'
            FileDescription = ''
            ProductName = ''
            ProductVersion = ''
            Copyright = ''
            PackageType = 'Service'
            ServiceName = "PSService"
            ServiceDisplayName = "PowerShell Service"
        }
    }
    
```

After building a service, you can install the service with the `--install` parameter of your service's executable. To uninstall a service, use the `--uninstall` parameter.&#x20;

### Package PowerShell 7.0

Creates an executable that contains the PowerShell 7.0 engine. This executable does not require the target machine have PowerShell or .NET Core installed. The size of the executable will be considerably larger than a typical `Merge-Script` executable.&#x20;

```powershell
@{
    Root = 'c:\Users\Adam\Desktop\script.ps1'
    OutputPath = 'c:\Users\Adam\Desktop\out'
    Package = @{
        Enabled = $true
        DotNetVersion = 'netcoreapp3.1'
        PowerShellVersion = "7.0.0"
    }
    Bundle = @{
        Enabled = $true
        Modules = $true
    }
}
```

### Package PowerShell 7.1&#x20;

You can package PowerShell 7.1 scripts by targeting .NET 5.0. You will need the [.NET 5.0 SDK or later](https://dotnet.microsoft.com/en-us/download/dotnet/5.0).&#x20;

```powershell
@{
    Root = 'c:\Users\Adam\Desktop\script.ps1'
    OutputPath = 'c:\Users\Adam\Desktop\out'
    Package = @{
        Enabled = $true
        DotNetVersion = 'net5.0'
        PowerShellVersion = "7.1.0"
    }
    Bundle = @{
        Enabled = $true
        Modules = $true
    }
}
```

### Package PowerShell 7.2

{% hint style="info" %}
PowerShell Pro Tools 2021.12.0 or later required.
{% endhint %}

You can package PowerShell 7.2 scripts by targeting .NET 6.0. You will need the [.NET 6.0 SDK or later](https://dotnet.microsoft.com/en-us/download/dotnet/6.0).&#x20;

```powershell
@{
    Root = 'c:\Users\Adam\Desktop\script.ps1'
    OutputPath = 'c:\Users\Adam\Desktop\out'
    Package = @{
        Enabled = $true
        DotNetVersion = 'net6.0'
        PowerShellVersion = "7.2.0"
    }
    Bundle = @{
        Enabled = $true
        Modules = $true
    }
}
```



## Bundle resources in a WPF application

Embeds the `image.png` file within the application so you can reference it in your XAML. This file resides in the same folder as `window.ps1`.

```
@{
    Root = 'c:\Users\Adam\Desktop\Window.ps1'
    OutputPath = 'c:\Users\Adam\Desktop\out'
    Package = @{
        Enabled = $true
        Resources = @("image.png")
    }
    Bundle = @{
        Enabled = $true
        Modules = $true
    }
}
```

In the XAML, you can reference the image like this.&#x20;

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
