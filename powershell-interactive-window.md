## PowerShell Interactive Window

The PowerShell Interactive Window provides a console like experience within Visual Studio. The interactive window can execute PowerShell scripts and commands, connect to remote machines and interact with the Visual Studio environment.

### Accessing the PowerShell Interactive Window

To access the PowerShell interactive window, click View-&gt;Other Windows-&gt;PowerShell Interactive Window. You can also use the default key combination Ctrl+Shift+\.

![](https://i0.wp.com/poshtools.com/wp-content/uploads/2017/07/view.png?resize=639%2C487&ssl=1)

### Executing Commands

You can execute commands in the PowerShell interactive window just like any other PowerShell prompt. PowerShell Tools IntelliSense is available in the interactive window. You can simply press enter to execute a command. The interactive window has access to the current PowerShell session. Any scripts run through the Visual Studio debugger will influence the environment of the interactive window. Variables and functions defined in these scripts can be called in the interactive window.

![](https://i1.wp.com/poshtools.com/wp-content/uploads/2017/07/execute.png?resize=866%2C127&ssl=1)

### Connecting to a Remote Machine

The interactive window can connect to a remote machine by clicking the Enter PowerShell Session button or using Enter-PSSession. Clicking the Enter PowerShell Session button will prompt you for a computer name.

![](https://i2.wp.com/poshtools.com/wp-content/uploads/2017/07/enterpssession.png?resize=278%2C134&ssl=1)

![](https://i2.wp.com/poshtools.com/wp-content/uploads/2017/07/computerName.png?resize=450%2C166&ssl=1)

You can then enter your credentials. You will be connected to the remote machine using Enter-PSSession.

You can disconnect from a remote session with the Exit PowerShell Session button.

![](https://i1.wp.com/poshtools.com/wp-content/uploads/2017/07/exitPssession.png?resize=312%2C120&ssl=1)

### Clear the Screen

You can clear the screen with the Clear Screen button.

![](https://i0.wp.com/poshtools.com/wp-content/uploads/2017/07/clearScreen.png?resize=242%2C118&ssl=1)

### Interact with Visual Studio

The Visual Studio DTE automation variable is available in the entire PowerShell session, including the interactive window, as $dte. The DTE object exposes useful functionality such as Solutions, Projects, Files, Commands and Windows.

![](https://i1.wp.com/poshtools.com/wp-content/uploads/2017/07/dte.png?resize=313%2C247&ssl=1)

