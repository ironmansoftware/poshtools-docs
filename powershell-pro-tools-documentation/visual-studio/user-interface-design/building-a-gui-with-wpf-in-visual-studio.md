# Building a GUI with WPF in Visual Studio

{% hint style="info" %}
Requires a [PowerShell Pro Tools](https://ironmansoftware.com/poshtools) license.&#x20;
{% endhint %}

## Building a GUI with WPF in Visual Studio

{% embed url="https://youtu.be/qh_GGiSkxnw" %}



## Applies to:

You will need the following:

* Visual Studio 2017, 2019 and 2022
* PowerShell Pro Tools for Visual Studio

## Creating a Project

You can create a module or script project.

Click File->New->Project

![](https://i0.wp.com/wandering.life/wp-content/uploads/2017/04/newproject.png?resize=581%2C155)

Select the Module, Forms or Script project type, name it and then click Ok.

![](<../../../.gitbook/assets/image (1) (2).png>)

![](<../../../.gitbook/assets/image (3).png>)

## Create the Form

Right click on your project and click Add and then New Item.

⚠ Warning ⚠ **Make sure you are selecting the Project and not the Solution when you right-click.**

![](https://i1.wp.com/wandering.life/wp-content/uploads/2017/04/newitem.png?resize=481%2C222)

Select the PowerShell WPF Window item template.

![](https://i2.wp.com/wandering.life/wp-content/uploads/2017/05/newWpfItem.png?resize=1024%2C709)

## Enabling IntelliSense&#x20;

You will need to add references to the following assemblies in order to use IntelliSense. This is also required for Visual Studio 2022 support.&#x20;

![](<../../../.gitbook/assets/image (81).png>)

## Working with the WPF Designer

### Getting Started

After creating the WPF Window, you should now see the designer surface and XAML code windows.

![](https://i2.wp.com/wandering.life/wp-content/uploads/2017/05/WpfDesigner.png?resize=1024%2C805)

A code behind file is automatically created that contains a PowerShell script capable of loading the XAML and running the WPF window.

![](https://i0.wp.com/wandering.life/wp-content/uploads/2017/05/codeBehind.png?resize=1200%2C226)

Pressing F5 or clicking the Start button on the menu will launch your WPF window.

![](https://i2.wp.com/wandering.life/wp-content/uploads/2017/05/debuggingWpf.png?resize=768%2C724)

### Adding Controls

You can add controls by editing the XAML or dragging and dropping tools from the Toolbox window.

To learn more about the WPF Designer, you can read [this tutorial](https://msdn.microsoft.com/en-us/library/hh921077.aspx) from Microsoft.

### Adding Event Handlers

In order to enable execution of actions based on different events, you’ll want to hook up some event handlers. To do so, the first thing you’ll need to do is name your control. Named controls are currently a requirement for event handlers.

![](https://i1.wp.com/wandering.life/wp-content/uploads/2017/05/myButton.png?fit=521%2C149\&ssl=1)

Next, select the event you would like wired up, enter a name for the event handler function and press enter.

![](https://i2.wp.com/wandering.life/wp-content/uploads/2017/05/addEventHandler.png?fit=675%2C453\&ssl=1)

The code behind generator will create a bunch of code to wire your event handler function to your control.

The first section removes the actual event handler XML attribute from the XAML. This is because PowerShell doesn’t actually support this type of event binding. I’ll look into supporting it somehow in the future but for now the event handlers in the XAML are placeholders for what is created in the code behind. They are removed at runtime.

![](https://i2.wp.com/wandering.life/wp-content/uploads/2017/05/RemoveEventHandlers.png?resize=1024%2C197)

The next piece of generated code is for variables that define the controls within your XAML. Currently, only the control you are adding an event handler for is generated in this section. In the future, all named controls will show up here. This allows PowerShell scripts to interact with the live controls.

![](https://i1.wp.com/wandering.life/wp-content/uploads/2017/05/controlVariables.png?resize=800%2C102)

Finally, we create an event handler function and wire it to the event on the control.

![](https://i2.wp.com/wandering.life/wp-content/uploads/2017/05/eventHandler.png?resize=800%2C294)

From here, we can define logic in the onClick function to take actions like opening a message box.

![](https://i0.wp.com/wandering.life/wp-content/uploads/2017/05/hey.png?resize=600%2C482)

### Packaging as an executable

XAML and the code behind script can be packaged as an executable. Simply right click on the WPF XAML window in the Solution Explorer window and select “Package as executable”.

## Adding an Icon to a Window

You cannot directly add icons to WPF windows with PowerShell and will need to do so using code. First, you'll need to ensure that your icon is in the same directory of the script. You will also need to add your icon as a resource.&#x20;

In your PowerShell Project, you can set the add the icon to your project and set it as a resource.&#x20;

First, right click on your project and Add an Existing Item to the project.&#x20;

<figure><img src="../../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

Next, right click on the icon you added and set the Resource property to true.&#x20;

<figure><img src="../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

Next, in your PS1 file for your WPF window, you will need to load your icon from either the file system or the packaged resources. The `Get-Resource` function below attempts to load from the packaged resource and, if not found, will instead load it from disk.&#x20;

```powershell
function Get-Resource {
     param($Name)
     
     $ProcessName = (Get-Process -Id $PID).Name
     try 
     {
        $Stream = [System.Reflection.Assembly]::GetEntryAssembly().GetManifestResourceStream("$ProcessName.g.resources")
        $KV = [System.Resources.ResourceReader]::new($Stream) | Where-Object Key -EQ $Name
        $Stream = $KV.Value
     } catch {}

    if (-not $Stream)
    {
        $Stream = [IO.File]::OpenRead("$PSScriptRoot\favicon.ico")
    }

    $Stream
}
```

Next, you'll need to create a new bitmap and set the window's icon property to the bitmap.&#x20;

```powershell
$bitmap = New-Object System.Windows.Media.Imaging.BitmapImage
$bitmap.BeginInit()
$bitmap.StreamSource = Get-Resource -Name 'favicon.ico'
$bitmap.EndInit()
$bitmap.Freeze()
 
$window.Icon = $bitmap
```

An entire working example of the PS1 file can be found below.&#x20;

```powershell
[System.Reflection.Assembly]::LoadWithPartialName("PresentationFramework") | Out-Null

function Import-Xaml {
	[xml]$xaml = Get-Content -Path $PSScriptRoot\WpfWindow1.xaml
	$manager = New-Object System.Xml.XmlNamespaceManager -ArgumentList $xaml.NameTable
	$manager.AddNamespace("x", "http://schemas.microsoft.com/winfx/2006/xaml");
	$xamlReader = New-Object System.Xml.XmlNodeReader $xaml
	[Windows.Markup.XamlReader]::Load($xamlReader)
}

$window = Import-Xaml

function Get-Resource {
     param($Name)
     
     $ProcessName = (Get-Process -Id $PID).Name
     try 
     {
        $Stream = [System.Reflection.Assembly]::GetEntryAssembly().GetManifestResourceStream("$ProcessName.g.resources")
        $KV = [System.Resources.ResourceReader]::new($Stream) | Where-Object Key -EQ $Name
        $Stream = $KV.Value
     } catch {}

    if (-not $Stream)
    {
        $Stream = [IO.File]::OpenRead("$PSScriptRoot\favicon.ico")
    }

    $Stream
}

$bitmap = New-Object System.Windows.Media.Imaging.BitmapImage
$bitmap.BeginInit()
$bitmap.StreamSource = Get-Resource -Name 'favicon.ico'
$bitmap.EndInit()
$bitmap.Freeze()
 
$window.Icon = $bitmap

$window.ShowDialog()
```

The result is a WPF window with a custom icon that is shown both when packaged and when running the script outside of the package.&#x20;

<figure><img src="../../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>
