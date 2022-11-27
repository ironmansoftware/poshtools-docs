---
description: Command your desktop with PSCommander.
---

# PSCommander

![](../.gitbook/assets/4a9c6a24400e45aea31c30b7b1f2bdf8.png)

{% hint style="danger" %}
PSCommander is now [free and open source](https://github.com/ironmansoftware/pscommander).&#x20;
{% endhint %}



PSCommander allows you to configure various Windows integration points and execute PowerShell script blocks when certain things happen on your desktop.&#x20;

{% embed url="https://youtu.be/Pzjr88j8yL4" %}

## Features

* CRON Schedules&#x20;
* Desktop Shortcuts
* Events
* Explorer Context Menu&#x20;
* File Associations&#x20;
* Global Hot Keys&#x20;
* Tray Icon and Menu

## Installation&#x20;

PSCommander is installed as a PowerShell module. You can install it from the PowerShell Gallery.&#x20;

```
Install-Module PSCommander
```

Once you have the module installed, you can cause PSCommander to run at logon by using the `Install-Commander` cmdlet.

```
Install-Commander
```

## Licensing&#x20;

PSCommander requires a PowerShell Pro Tools license. If you already have a license installed, you will be able to use PSCommander. You can also use the `Install-CommanderLicense` cmdlet to install your license file.&#x20;

```
Install-CommanderLicense -Path .\license.txt
```

## Configuration

PSCommander is configured using a single PS1 file. This file is stored within your documents folder. To create a new config file, you can use the following command.&#x20;

```
$Documents = [Environment]::GetFolderPath('MyDocuments')
$Commander = Join-Path $Documents 'PSCommander'
New-Item $Commander -ItemType Directory 
New-Item (Join-Path $Commander 'config.ps1')
```

PSCommander will use this configuration file to load settings. Any changes to the file will result in PSCommander reconfiguring itself. If you don't have PSCommander running yet, you can use `Start-Commander`.

```
Start-Commander 
```

The following sections outline the commands you can use within the `config.ps1` file. These cmdlets will not work outside of PSCommander.&#x20;

## Features&#x20;

### CRON Schedules&#x20;

PSCommander allows you to run script blocks based on CRON schedules. Note that PSCommander uses a single runspace. Long running scripts are not recommended for use with PSCommander.&#x20;

To create a CRON schedule, use `New-CommanderSchedule` within the `config.ps1`file. For example, this configuration will create a schedule that opens notepad every minute.&#x20;

You can use a site like [crontab guru](https://crontab.guru/) to define schedules.

```
New-CommanderSchedule -CronExpression "* * * * *" -Action {
     Start-Process Notepad
}
```

### Custom Protocol Handlers

A custom protocol handler can cause a PSCommander action to be taken from a website or other invocation of the custom protocol.&#x20;

To define a custom protocol, you can use the `New-CommanderCustomProtocol`. The `$args[0]` parameter will have the URL that was clicked.&#x20;

```
New-CommanderCustomProtocol -Protocol myApp -Action {
     if ($args[0] -eq 'notepad') { Start-Process notepad }
     if ($args[0] -eq 'calc') { Start-Process calc }
     if ($args[0] -eq 'wordpad') { Start-Process wordpad }
}
```

To use the custom protocol, you can include regular links in websites and it will invoke PSCommander remotely.&#x20;

```
<html>
  <body>
    <a href="myApp://notepad">Start Notepad</a>
  </body>
</html>
```

![](../.gitbook/assets/protocol.gif)

### Data Sources

Data sources allow you to load data a single time and use it with multiple desktop widgets. This provides better performance than loading the data in each widget. It also provides data binding support for WPF components.&#x20;

To register a data source, use the `Register-CommanderDataSource` cmdlet. The below data source loads computer performance information. It loads the data every 5 seconds.&#x20;

```
Register-CommanderDataSource -Name 'ComputerInfo' -LoadData {
   $Stats = Get-NetAdapterStatistics
   $NetworkDown = 0
   $Stats.ReceivedBytes | Foreach-Object { $NetworkDown += $_ } 
   
   $NetworkUp = 0
   $Stats.SentBytes | Foreach-Object { $NetworkUp += $_ } 
    
   @{
       CPU = Get-CimInstance Win32_Processor | Measure-Object -Property LoadPercentage -Average | Select-Object -Expand Average
	   Memory = (Get-Counter '\Memory\Available MBytes').CounterSamples.CookedValue
	   NetworkUp = $NetworkUp / 1KB
	   NetworkDown = $NetworkDown / 1KB
   }
} -RefreshInterval 5
```

To use this data source with a desktop widget, you'll need to use the `-DataSource` parameter for a custom widget. Every time the data source is updated, the WPF custom widget will be notified and will load UI components.&#x20;

This example creates a small, grey bar that formats and displays the computer information.

```
New-CommanderDesktop -Widget @(
   New-CommanderDesktopWidget -LoadWidget {
       [xml]$Form = Get-Content C:\Users\adamr\Desktop\test.xaml -Raw
		   $XMLReader = (New-Object System.Xml.XmlNodeReader $Form)
		   [Windows.Markup.XamlReader]::Load($XMLReader)
   } -Height 200 -Width 1400 -Top 20 -Left 100 -DataSource 'ComputerInfo'
}
```

The XAML can take advantage of binding to the hashtable created by the data source.&#x20;

```
<Window 
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    WindowStyle="None"
    ResizeMode="NoResize"
    Background="Transparent"
    Height="200"
    Width="1900"
>
    <Grid Margin="10">
        <Border BorderBrush="#333333" BorderThickness="1" Background="#333333" Grid.Column="1"
                CornerRadius="10" VerticalAlignment="Center"
                HorizontalAlignment="Stretch">
            <Grid Margin="10">

                <Grid.ColumnDefinitions>
                    <ColumnDefinition Width="200"/>
                    <ColumnDefinition Width="200"/>
                    <ColumnDefinition Width="300"/>
                    <ColumnDefinition Width="300"/>
                </Grid.ColumnDefinitions>

                <Grid.RowDefinitions>
                    <RowDefinition />
                    <RowDefinition Height="Auto" />
                </Grid.RowDefinitions>
                <TextBlock DataContext="{Binding CurrentValue}" Text="{Binding CPU, StringFormat=CPU: {0}%}" TextWrapping="Wrap" Margin="5" Foreground="#28bf37" FontFamily="Consolas" Grid.Column="0"/>
                <TextBlock DataContext="{Binding CurrentValue}" Text="{Binding Memory, StringFormat=Available Memory: {0:N0} MB}" TextWrapping="Wrap" Margin="5" Foreground="#28bf37" FontFamily="Consolas" Grid.Column="1"/>
                <TextBlock DataContext="{Binding CurrentValue}" Text="{Binding NetworkUp, StringFormat=Network Up: {0:N0} KB\s}" TextWrapping="Wrap" Margin="5" Foreground="#28bf37" FontFamily="Consolas" Grid.Column="2"/>
                <TextBlock DataContext="{Binding CurrentValue}" Text="{Binding NetworkDown, StringFormat=Network Down: {0:N0} KB\s}" TextWrapping="Wrap" Margin="5" Foreground="#28bf37" FontFamily="Consolas" Grid.Column="3"/>
            </Grid>
        </Border>
    </Grid>
</Window>
```

This produces a widget that looks like this.&#x20;

![](<../.gitbook/assets/image (64).png>)

### Desktop Widgets

PSCommander providers a desktop widget system that allows you to place text, images, web pages, custom WPF windows and measurement counters on the desktop. It is a similar experience to SysInternals bginfo and Rainmeter.&#x20;

All widgets are created using the `New-CommanderDesktopWidget` cmdlet in combination with the `New-CommanderDesktop` or `Set-CommanderDesktop` cmdlets.&#x20;

![](../.gitbook/assets/desktop.gif)

#### Text Widget

The following example creates a text widget with some computer information.

```
$CI = Get-ComputerInfo

$ComputerInfo = @"
	Number of Processes: $($CI.OsNumberOfProcesses)
	Number of Users: $($CI.OsNumberOfUsers)
	User Name: $($CI.CsUserName)
	System Family: $($CI.CsSystemFamily)
"@

New-CommanderDesktop -Widget @(
   New-CommanderDesktopWidget -Text $ComputerInfo -Height 300 -Width 1000 -FontSize 30 -Top 500 -Left 500 -FontColor 'Black'
)
```

#### Image Widget

The following example creates an image widget on the desktop.

```
New-CommanderDesktop -Widget @(
   New-CommanderDesktopWidget -Image 'C:\src\blog\content\images\news.png' -Height 200 -Width 200 -Top 200 
)
```

#### Webpage Widget

The following example creates a webpage widget on the desktop.

```
New-CommanderDesktop -Widget @(
   New-CommanderDesktopWidget -Url 'https://www.google.com' -Height 500 -Width 500 -Top 400
)
```

#### Custom WPF Widget

The following example creates a custom WPF widget on the desktop.

```
New-CommanderDesktop -Widget @(
   New-CommanderDesktopWidget -LoadWidget {
       [xml]$Form = "<Window xmlns=`"http://schemas.microsoft.com/winfx/2006/xaml/presentation`"><Grid><Label Content=`"Hello, World`" Height=`"30`" Width=`"110`"/></Grid></Window>"
		$XMLReader = (New-Object System.Xml.XmlNodeReader $Form)
		[Windows.Markup.XamlReader]::Load($XMLReader)
   } -Height 200 -Width 200 -Top 200 -Left 200
)
```

#### Measurement Widget

The following creates a measurement widget on the desktop.

```
New-CommanderDesktop -Widget @(
   New-CommanderDesktopWidget -LoadMeasurement {Get-Random} -MeasurementTitle 'Random' -MeasurementSubtitle 'A random number' -MeasurementUnit 'units' -Height 300 -Width 500 -Left 600 -Top 200 -MeasurementFrequency 1 -MeasurementDescription "Nice" -MeasurementTheme 'DarkBlue'
)
```

### Desktop Shortcuts

PSCommander can create desktop shortcuts that will execute PowerShell when clicked. Desktop shortcuts require the PSCommander is running so you may want to use `Install-Commander` to ensure that it has been started before a user clicks a shortcut.&#x20;

You can configure the text, description and icon for the shortcut. This example creates a desktop shortcut that opens notepad when clicked.&#x20;

```
New-CommanderShortcut -Text 'Click Me' -Description 'Nice' -Action {
    Start-Process notepad
}
```

### Events

PSCommander can register event handlers that invoke script blocks based on events happening within your system. You can use the `Register-CommanderEvent` cmdlet to listen to these events.

The following example starts notepad when commander starts.

```
Register-CommanderEvent -OnCommander Start -Action {
   Start-Process notepad
}
```

You can also listen to events that are happening with Windows using WMI event filters. This example will use the built-in `ProcessStarted` event to run a script block whenever a process is started. This example writes to a file. The `$args[0]` is the WMI object that was created.&#x20;

```
Register-CommanderEvent -OnWindows ProcessStarted -Action {
   $Args[0]['Name'] | Out-File C:\users\adamr\desktop\process-name.txt
}
```

If you want to configure a custom WMI event, you can use the `-WmiEventType` and `-WmiEventFilter` parameters to listen for those events.&#x20;

```
Register-CommanderEvent -OnWindows WmiEvent -WmiEventType '__InstanceCreationEvent' -WmiEventFilter 'TargetInstance isa "Win32_Process"' -Action {
   $Args[0]['Name'] | Out-File C:\users\adamr\desktop\process-name.txt
}
```

### Explorer Context Menus&#x20;

PSCommander can create context menu items that appear when right clicking on folders and files within Windows Explorer. Your script block will receive the path to the folder or file via the `$Args[0]` variable.&#x20;

You can create context menu items that appear on folders or only apply to particular extensions of files.&#x20;

This example creates a context menu that displays as Click Me and opens VS Code to the file that was clicked.

```
New-CommanderContextMenu -Text 'Click me' -Action {
    Start-Process code -ArgumentList $args[0]
}
```

### File Associations

PSCommander allows you to associate files with script blocks defined within the commander configuration. You can define the extension and action to take when the file type is open. You will receive the full file path in the `$Args[0]` variable.&#x20;

This example opens VS Code based on the file that was opened and associates it with the `.ps2` file extension.&#x20;

```
New-CommanderFileAssociation -Extension ".ps2" -Action {
    Start-Process code -ArgumentList $Args[0]
}
```

### Global Hot Keys

PSCommander allows you to associate global hot keys to PowerShell actions.&#x20;

This example defines a hot key that is invoked whenever the `Ctrl+T` key combo is pressed. Note that key combinations cannot interfere with other pre-existing combinations.&#x20;

```
New-CommanderHotKey -Key 'T' -ModifierKey 'Ctrl' -Action { 
    Start-Process notepad
}
```

### Tray Icon and Menu

PSCommander provides configuration for the tray icon. You can define the hover text and the icon that is displayed. You can choose to hide the Exit and Edit Config options and define your own right click menus.&#x20;

Tray menu items can invoke script actions and you can define menu items dynamically. This example creates some menu items statically and dynamically.

```
New-CommanderToolbarIcon -MenuItem @(
    New-CommanderMenuItem -Text 'Notepad' -Action {
        Start-Process notepad
    } -MenuItem @(
        New-CommanderMenuItem -Text 'Subnotepad' -Action {
            Start-Process notepad
        }
    ) -LoadMenuItems {  
        New-CommanderMenuItem -Text 'Dynamic SubNotepad' -Action {
            Start-Process notepad
        }
    }
) -LoadMenuItems {
    New-CommanderMenuItem -Text 'Dynmaic Notepad' -Action {
        Start-Process notepad
    }
}
```
