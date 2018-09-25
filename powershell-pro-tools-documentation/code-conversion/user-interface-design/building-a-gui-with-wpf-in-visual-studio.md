## Building a GUI with Windows Forms in Visual Studio

## 

## Applies to:

You will need the following:

* Visual Studio 2015 and Visual Studio 2017
* PowerShell Pro Tools for Visual Studio 2015 and 2017

## Creating a Project

You can create a module or script project.

Click File-&gt;New-&gt;Project

![](https://i0.wp.com/wandering.life/wp-content/uploads/2017/04/newproject.png?resize=581%2C155)

Select the Module or Script project type, name it and then click Ok.

![](https://i1.wp.com/wandering.life/wp-content/uploads/2017/04/newproject2.png?resize=753%2C522)

## Create the Form

Right click on your project and click Add and then New Item. 

![](https://i1.wp.com/wandering.life/wp-content/uploads/2017/04/newitem.png?resize=481%2C222)

Select the PowerShell WPF Window item template.

![](https://i2.wp.com/wandering.life/wp-content/uploads/2017/05/newWpfItem.png?resize=1024%2C709)

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

![](https://i1.wp.com/wandering.life/wp-content/uploads/2017/05/myButton.png?fit=521%2C149&ssl=1)

Next, select the event you would like wired up, enter a name for the event handler function and press enter.

![](https://i2.wp.com/wandering.life/wp-content/uploads/2017/05/addEventHandler.png?fit=675%2C453&ssl=1)

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