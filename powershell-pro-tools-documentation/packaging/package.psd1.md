# Package.psd1

{% hint style="info" %}
Requires [PowerShell Pro Tools](https://ironmansoftware.com/poshtools)
{% endhint %}

## About

This about file contains information about using hashtables and PSD1 files to configure Merge-Script. These psd1 files are also used by PowerShell Tools for Visual Studio Code. 

### Config File Schema

```text
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
        }
        Bundle = @{
            Enabled = $true # Whether to bundle multiple PS1s into a single PS1. Always enabled when Package is enabled. 
            Modules = $true # Whether to bundle modules into the package
        }
    }
    
```

### Using a config file

A config file can be used either from within a PowerShell script as a hashtable or imported from a PSD1 file containing the hashtable.

## EXAMPLES

It is not required to include all aspects of the config when using Merge-Script. The only required components are Root and OutputPath. Aside from that, anything that is not include will be considered false. This means that in the below example, packaging is disabled but bundling is not. The below operation will not bundle nested modules or required assemblies of any modules it is bundling.

```text
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

Creates a PowerShell console based application that has an application icon and hides the console window. 

```text
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

Creates a PowerShell service based on the service.ps1 file and outputs to the out directory on the desktop. It will use the .NET 4.6.2 Developer Pack. The service name will be PSService and the display name will be PowerShell Service. 

For more information on services, see the [Package as Service](package-a-service.md) section.

```text
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

After building a service, you can install the service with the `--install` parameter of your service's executable. To uninstall a service, use the `--uninstall` parameter. 

### Bundle PowerShell Core Engine with your Script

Creates an executable that contains the PowerShell Core engine. This executable does not require the target machine have PowerShell Core or .NET Core installed. The size of the executable will be considerably larger than a typical `Merge-Script` executable. 

```text
@{
    Root = 'c:\Users\Adam\Desktop\script.ps1'
    OutputPath = 'c:\Users\Adam\Desktop\out'
    Package = @{
        Enabled = $true
        PowerShellCore = $true
    }
    Bundle = @{
        Enabled = $true
        Modules = $true
    }
}
```

