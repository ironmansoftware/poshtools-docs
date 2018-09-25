## Initialization

The main entry point for the PowerShell Tools is the PowerShellTools.PowerShellToolsPackage class. This class is responsbile for registering all the different components during VSIX installation and initializing the out-of-proc PowerShell Host that executes scripts and runs IntelliSense. The VSIX is loaded when a PowerShell project is loaded or the PowerShell Interactive Window is opened.

During startup, the out-of-process host executable is initialized with a unique GUID to identify it, the process ID of the Visual Studio instance that started it and a "ready event" unique name to communicate back to Visual Studio when it has fully loaded. The host then starts the IntelliSense, Debugging and Command Explorer services, binds them to WCF channels with NetNamedPipeBindings and signals back to Visual Studio that it is ready to run. The host process subscribes to the Exited event of the Visual Studio process to enable it to exit when Visual Studio terminates.

After host initialization, commands are registered with the system that allow for functionality such as Executing Selections, opening the PowerShell Interactive window and executing from the Solution Explorer.





