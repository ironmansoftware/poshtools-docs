## Package as Executable

PowerShell Pro Tools supports packaging PowerShell scripts as executables. The packaging functionality creates a .NET executable and embeds the PowerShell script into the assembly. The .NET executable takes advantage of the PowerShell console host to run the script. The host supports accepting arguments from the command line and all the functionality of PowerShell.exe in your own custom executable.

### Benefits of Packaging

Packaging enables easy distribution of PowerShell scripts in easy to consume executables. Scripts cannot be changed and can be provided to end users without the worry of what may happen if they modify them.

### Packaging Steps

Assume we have a simple script that accepts a couple parameters and outputs to the screen.

![](https://i1.wp.com/poshtools.com/wp-content/uploads/2017/05/script.png?resize=767%2C225&ssl=1)

To package the script as an executable, right click on the script in Solution Explorer and select Package as executable.

![](https://i0.wp.com/poshtools.com/wp-content/uploads/2017/05/packageAsExe.png?resize=654%2C307&ssl=1)

Output from the packaging process will be written to the Build output pane in the Output window.

![](https://i0.wp.com/poshtools.com/wp-content/uploads/2017/05/output.png?resize=1024%2C97&ssl=1)

The resulting executable will behave similar to PowerShell.exe but will pass arguments from the command line into your packaged script. Since the source script accepts a Message and a NumberOfTimes parameter in the above example, the host executable accepts these parameters as well.

![](https://i2.wp.com/poshtools.com/wp-content/uploads/2017/05/result.png?resize=716%2C415&ssl=1)

### Technical Considerations

Packaging Requires .NET Core SDK version 1.0.0 or higher.

Resulting executables can be run on machines running PowerShell v3 or greater.

Resulting executables run under the .NET 4.6.2 framework.

