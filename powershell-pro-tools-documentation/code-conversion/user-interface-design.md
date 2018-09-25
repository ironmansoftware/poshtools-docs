## Building a GUI with WPF in Visual Studio

## 

## Applies to:

* Visual Studio 2017 and 2015
* PowerShell Pro Tools for Visual Studio 2015 and 2017

## Creating a Project

You can create a module or script project.

Click File-&gt;New-&gt;Project

![](https://i0.wp.com/wandering.life/wp-content/uploads/2017/04/newproject.png?resize=581%2C155)

Select the Module or Script project type, name it and then click Ok.

Right click on your project to create a new file and select the PowerShell WPF Window item template.

![](https://i2.wp.com/wandering.life/wp-content/uploads/2017/05/newWpfItem.png?resize=778%2C539)

After creating your WPF window, you will see the same designer you would for a C\# or VB.NET project.

![](https://i2.wp.com/wandering.life/wp-content/uploads/2017/05/WpfDesigner.png?resize=728%2C572)

A code behind file is automatically created that contains a PowerShell script capable of loading the XAML and running the WPF window.

![](https://i0.wp.com/wandering.life/wp-content/uploads/2017/05/codeBehind.png?resize=937%2C175)

Pressing F5 or clicking the Start button on the menu will launch your WPF window.

![](https://i2.wp.com/wandering.life/wp-content/uploads/2017/05/debuggingWpf.png?resize=617%2C582)‘

## Wiring up Event Handlers

In order to enable execution of actions based on different events, you’ll want to hook up some event handlers. To do so, the first thing you’ll need to do is name your control. Named controls are currently a requirement for event handlers.

![](https://i1.wp.com/wandering.life/wp-content/uploads/2017/05/myButton.png?resize=521%2C149)

Next, select the event you would like wired up, enter a name for the event handler function and press enter.

![](https://i2.wp.com/wandering.life/wp-content/uploads/2017/05/addEventHandler.png?resize=527%2C354)

The code behind generator will create a bunch of code to wire your event handler function to your control.

The first section removes the actual event handler XML attribute from the XAML. This is because PowerShell doesn’t actually support this type of event binding. I’ll look into supporting it somehow in the future but for now the event handlers in the XAML are placeholders for what is created in the code behind. They are removed at runtime.

![](https://i2.wp.com/wandering.life/wp-content/uploads/2017/05/RemoveEventHandlers.png?resize=726%2C140)

The next piece of generated code is for variables that define the controls within your XAML. Currently, only the control you are adding an event handler for is generated in this section. In the future, all named controls will show up here. This allows PowerShell scripts to interact with the live controls.

![](https://i1.wp.com/wandering.life/wp-content/uploads/2017/05/controlVariables.png?resize=722%2C92)

Finally, we create an event handler function and wire it to the event on the control.

![](https://i2.wp.com/wandering.life/wp-content/uploads/2017/05/eventHandler.png?resize=648%2C238)

From here, we can define logic in the onClick function to take actions like opening a message box.

![](https://i0.wp.com/wandering.life/wp-content/uploads/2017/05/hey.png?resize=522%2C419)

## Packaging as an executable

XAML and the code behind script can be[packaged as an executable](https://poshtools.com/docs/posh-pro-tools/package-as-executable/). Simply right click on the WPF XAML window in the Solution Explorer window and select “Package as executable”.

