# PowerShell Interactive Window

The PowerShell Interactive Window provides a console like experience within Visual Studio. The interactive window can execute PowerShell scripts and commands, connect to remote machines and interact with the Visual Studio environment.

## Accessing the PowerShell Interactive Window

To access the PowerShell interactive window, click View->Other Windows->PowerShell Interactive Window. You can also use the default key combination Ctrl+Shift+.

![](<../../.gitbook/assets/image (31).png>)

## Executing Commands

You can execute commands in the PowerShell interactive window just like any other PowerShell prompt. PowerShell Tools IntelliSense is available in the interactive window. You can simply press enter to execute a command. The interactive window has access to the current PowerShell session. Any scripts run through the Visual Studio debugger will influence the environment of the interactive window. Variables and functions defined in these scripts can be called in the interactive window.

## Connecting to a Remote Machine

The interactive window can connect to a remote machine by clicking the Enter PowerShell Session button or using Enter-PSSession. Clicking the Enter PowerShell Session button will prompt you for a computer name.

You can then enter your credentials. You will be connected to the remote machine using Enter-PSSession.

You can disconnect from a remote session with the Exit PowerShell Session button.

## Clear the Screen

You can clear the screen with the Clear Screen button.

## Interact with Visual Studio

The Visual Studio DTE automation variable is available in the entire PowerShell session, including the interactive window, as $dte. The DTE object exposes useful functionality such as Solutions, Projects, Files, Commands and Windows.
