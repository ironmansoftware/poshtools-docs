The PowerShell Pro Tools PowerShell module automatically adds commands to Visual Studio Code when loaded into the editor. These commands allow you to convert code to C\# and PowerShell as well as bundle and package scripts. You will need the PowerShell extension for Visual Studio Code installed. 

### Accessing the PowerShell Pro Tools Commands 

Import the PowerShell Pro Tools module with Import-Module within VS Code. 

`Import-Module PowerShellProTools`

You can access the commands by using the Command Palette \(Ctrl+Shift+P\) and executing the "PowerShell: Show Additional Commands from PowerShell Modules" command. ![](/assets/powershell-additonal-commands)

After executing this command, you will see a list of all the additional commands loaded into the VS Code PowerShell extension. This will include the PowerShell Pro Tools commands. ![](/assets/powershell-pro-tools-commands)

### Bundle Script

Bundle script will bundle the current script. This bundles any imported modules, dot sourced scripts, nested modules and required assemblies. The bundled script will be output to an Output folder in the same directory as the script you are bundling. When you execute this command, it executes on the current file open in the editor. 

### Convert to C\#

Converts the current file to C\# code. This assumes you are executing against PowerShell script. When you execute this command, it executes on the current file open in the editor. The file is not renamed. 

### Convert to PowerShell

Converts the current file to PowerShell script. This assumes you are executing against C\# code. When you execute this command, it executes on the current file open in the editor. The file is not renamed. 

### Package script as executable

Packages the current file as an executable. This bundles any imported modules, dot sourced scripts, nested modules and required assemblies. This also obfuscates the executable. The packaged script will be output to an Output folder in the same directory as the script you are bundling. When you execute this command, it executes on the current file open in the editor. 

