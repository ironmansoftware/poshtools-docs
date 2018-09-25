## Project Structure

### PowerShellTools.csproj

Main project for the core VSIX. This project contains most of the Visual Studio integration including the project system, IntelliSense, syntax highlighting, debug engine, snippet manager, project templates and options dialogs. 

### PowerShellTools.Comon.csproj

Shared code between the PowerShell extension and the out-of-process PowerShell host that runs the PowerShell scripts, IntelliSense and debugging. 

### PowerShellTools.Contracts.csproj

Interfaces that define the WCF contracts between the PowerShell extension and the out-of-process PowerShell host. 

### PowerShellTools.Explorer.csproj

Implementation of the PowerShell Command Explorer tool window. 

### PowerShellTools.HostService.csproj

Out-of-process executable responsible for executing PowerShell scripts, the IntelliSense and the debugger. Communicates to the PowerShell extension via WCF. 

### PowerShellTools.HostService.x86.csproj

The x86 version of the out-of-process executable. This process is started when the user changes to x86 mode in the Visual Studio options dialog. 

### PowerShellTools.MSBuild.csproj

MSBuild tasks for PowerShell Tools. 

### PowerShellTools.Repl.csproj

A fork of the C\# interactive window that creates the PowerShell Interactive window for PowerShell Tools. This project is packaged as its own VSIX. 

### PowerShellTools.TestAdapater.csproj

PowerShell test adapter for the Visual Studio Test Manager window. Executes Pester tests. 



