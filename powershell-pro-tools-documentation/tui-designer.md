---
description: Terminal User Interface designer for PowerShell
---

# TUI Designer

{% hint style="warning" %}
The TUI Designer is currently in **beta**.
{% endhint %}

The Terminal User Interface \(TUI\) designer is used for designing UIs that run within standard terminals. They output script that works with [Terminal.Gui](https://github.com/migueldeicaza/gui.cs). This project allows for the creation of UIs that run on Windows, Linux and Mac. You can even run terminals in shells like Azure Cloud Shell. 

## Overview

The TUI Designer is a console application based on Terminal.Gui. You can download the designer from our [downloads](https://ironmansoftware.com/downloads) page. To create a GUI, open the designer application by launching `Terminal.Gui.Designer`.

The TUI designer is broken into 4 sections. On the left, you have the following.

* Toolbox - Contains available controls that can be added to the window
* Properties - Allows for editing for selected controls 
* Controls - Contains a list of controls defined in the Window

The right side of the designer is the design surface and displays the current window and any controls that are added to it. 

![](../.gitbook/assets/image%20%2862%29.png)

## Designing a TUI

To design a TUI, you take advantage of the sections defined above. To add new controls, double click on the control listed in the Toolbox and it will be added to the form. 

![Adding a control](../.gitbook/assets/addcontrol.gif)

Once the control has been added, it will appear within the designer window and within the list of Controls. Some default properties will be set for the control. You can move the control around the window by clicking and dragging it. When moving a control like this, it will set the absolute positioning of the control. 

![Moving a control](../.gitbook/assets/drag.gif)

When you select a control, the Properties view will update with all the available properties that you can set for the control. Some properties have special dialogs that will open to allow you to modify more complex objects. Properties like sizes and positioning can be used to create calculated layouts. You can also easily set text and IDs. 

![Setting Properties](../.gitbook/assets/properties%20%281%29.gif)

Once you have completed designing your control, you can save the file as a PS1 file. The PS1 file will contain a PowerShell script that will display the same TUI. 

![Save a TUI](../.gitbook/assets/save.gif)

## Running a TUI

To run a TUI, you will need to install the `Microsoft.PowerShell.ConsoleGuiTools` module. This module contains the Terminal.Gui assembly. 

```text
Install-Module Microsoft.PowerShell.ConsoleGuiTools
```

Next, you will need to load the Terminal.Gui assembly and initialize the application.

```text
$guiTools = (Get-Module Microsoft.PowerShell.ConsoleGuiTools -List).ModuleBase
Add-Type -Path (Join-path $guiTools Terminal.Gui.dll)
[Terminal.Gui.Application]::Init()
```

The script that is generate with the TUI designer will return a Window object that you can use in your application. Invoke your script and add it to the application. Do not modify the script directly. It will be overridden if you use the designer again and the designer may not be able to load the script if you modify it. 

```text
$Window = .\tui.ps1
[Terminal.Gui.Application]::Top.Add($Window)
```

Finally, you can start your application by calling `Run`.

```text
[Terminal.Gui.Application]::Run()
```

## Adding Event Handlers

To add interaction to your TUI, you will need to add event handlers. You can learn about all the events the are available by visiting the [Terminal.Gui documentation](https://migueldeicaza.github.io/gui.cs/api/Terminal.Gui/Terminal.Gui.Button.html). 

For example, if you want to add a click event to a button, you could do the following. Variables for each one of your controls will be defined based on their ID. 

```text
$View0.add_Clicked({[Terminal.Gui.MessageBox]::Query("Hello", "")})
```

![Event Handlers](../.gitbook/assets/run.gif)

