# Package as Service

{% hint style="info" %}
Requires [PowerShell Pro Tools](https://ironmansoftware.com/poshtools)
{% endhint %}

The PowerShell Pro Tools package can create Windows services based on PS1 files. It has all the same options as other exectuables but requires a special entry point script. This script should be used at the `Root` value when using `Merge-Script` or the Entry Point when packaging through Visual Studio. 

```text
<#
	This function is called when the service is started. Once this function returns, 
	your service will be set to a Running state.
#>
function OnStart() {

}

<#
	This function is called when the service is started. Once this function returns,
	your service will be set to a Stoppe state and the process will terminate.
#>
function OnStop() {

}

# Specifies whether this service can be stopped once started
$CanStop = $true
```

## OnStart Function

The `OnStart` function will be called when the service is started. You should not block the execution of this function. If you need to start a background process, consider using `Start-Job` . Once the function returns, the service will be listed as running in Service Control Manager. 

You will have access to a `$Service` variable within the `OnStart` function that is the [ServiceBase ](https://docs.microsoft.com/en-us/dotnet/api/system.serviceprocess.servicebase?view=netframework-4.8)instance for your service.

## OnStop Function

The `OnStop` function will be called when the Service Control Manager attempts to stop the service. You can do any clean up of resources for your service in this function. This would be a good place to stop any jobs using `Stop-Job`.

You will have access to a `$Service` variable within the `OnStop` function that is the [ServiceBase ](https://docs.microsoft.com/en-us/dotnet/api/system.serviceprocess.servicebase?view=netframework-4.8)instance for your service.

## CanStop Variable

You can set the `$CanStop` variable to either `$true` or `$false`. If set to `$false`, the service cannot be stopped by the Service Control Manager.

## Arguments

PowerShell services have access to both the process arguments and the service startup parameters. You can access the process arguments by referencing the `$ProcessArgs` variable. You can access the service startup parameters by accessing the `$ServiceArgs` variable. 

## Installing a Service

You can install your service by passing `--install` to the service's executable. Install will not start the service so use Start-Service to start your new service by the name you provided. 

## Uninstall a Service

To uninstall a service, use the `--uninstall` flag for your service's executable. It will also take care of stopping the service. 

