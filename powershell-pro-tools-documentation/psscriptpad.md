# PSScriptPad

PSScriptPad is the tiny editor for Windows PowerShell. It requires no installation or configuration. It weighs in around 4Mbs, can editor and execute PowerShell scripts, design Windows Forms and Package Executables. 

## Download

You can [download PSScriptPad from our website](https://ironmansoftware.com/downloads). It is just a .exe file. 

## Editing PowerShell

PSScriptPad supports editing PowerShell scripts. It supports syntax highlighting, syntax checking, IntelliSense and code folding. 

#### Creating a New PowerShell File

Click the New File button on the toolbar to create a new file. 

![](../.gitbook/assets/image%20%2824%29.png)

#### Opening a PowerShell Script

Click the Open File button on the toolbar to open a script. 

![](../.gitbook/assets/image%20%2823%29%20%281%29.png)

#### IntelliSense 

IntelliSense is automatically invoked. It will complete PowerShell cmdlet names, variables, paths, and parameter names. You can also press `Ctrl+Space` to manually invoke IntelliSense. As you type, the IntelliSense list will be filtered. Pressing tab will select and insert the current option. 

![](../.gitbook/assets/image%20%2822%29%20%281%29.png)

#### Code Folding 

Code Folding collapses blocks of PowerShell script that you wish to hide. You can collapse blocks such as if blocks, script blocks and functions blocks. Just click the minus and plus sign to close and open blocks. 

![](../.gitbook/assets/image.png)

## Debugging 

PSScriptPad can also debug PowerShell scripts. It supports executing scripts, setting breakpoints, stepping through scripts and viewing the output of scripts in the terminal window. 

### Setting a breakpoint 

You can set breakpoints by clicking in the editor margin or by using the `F9` button to toggle a breakpoint on the selected line. 

![Set a breakpoint](../.gitbook/assets/set-breakpoint.gif)

### Running a Script

You can run a script by clicking the Run button or by pressing `F5`. It will run the currently open tab. 

![Run a script](../.gitbook/assets/run-script.gif)

### Stepping through a script

You can single step through a script using the following keys:

* `F10` - Step over
* `F11` - Step Into
* `Shift+F11` - Step Out

![Stepping in a script](../.gitbook/assets/stepping.gif)

## Packaging Scripts

PSScriptPad can package scripts to executables using [package.psd1](packaging/package.psd1.md) files or by selecting a PS1 file and packaging with the default settings. 

### Packaging Without a Package.PSD1 file

You can select an PS1 file and click the package button and the script will be packaged into an executable. Results of the packaging process will be shown within the Console. 

![Package Script](../.gitbook/assets/package.gif)

### Packaging with a Package.PSD1 File

[Package.psd1](packaging/package.psd1.md) files allow you to configure all the settings for the packaging process. You can create a package.psd1 file and then when you click the Package button, it will use that file for configuration.

![Package.PSD1](../.gitbook/assets/packagepsd1.gif)



## Windows Form Designer

The Windows Form Designer allows you to create forms with PowerShell scripts. 

### Creating a new Form

You can create a new form by click the drop arrow next to the new file button and click New Windows Form.

![New Windows Form](../.gitbook/assets/new-form.gif)

### Adding Controls to a Form

You can add controls to a form by expanding the toolbox pane, clicking the control you'd like to add and then clicking on the form.

![Adding Controls to a Form](../.gitbook/assets/add-controls.gif)

### Setting Properties of Controls

You can set the properties of a control by selecting the control and then modifying properties in the Properties pane. 

![Set Properties of a Control](../.gitbook/assets/setprops.gif)

### Setting Event Handlers

You can set event handlers for a control by selecting the control, clicking the lightening bolt icon in the Properties pane and then typing the name of the event handler for the event you'd like to hook up. After saving the form, you can view the code-behind file to define what happens when the event takes place. 

![Setting an Event Handler](../.gitbook/assets/setevents.gif)

### Running a Form

You can run a form by open the PS1 file for your form and pressing `F5` or by clicking the run button. 

![Running a Form](../.gitbook/assets/run-form.gif)

## WPF Designer

{% hint style="warning" %}
The WPF designer is coming in a future version of PSScriptPad.
{% endhint %}

The WPF designer allows you to visually create WPF forms. You can use the inline editor to adjust properties of the form and see it update in real time. You can then use the XAML in your PowerShell scripts.

### Create a WPF Form

Click the New WPF Form button to create a new WPF form. It will open the WPF designer.

![WPF Editor in PSScriptPad](../.gitbook/assets/wpf.gif)

### Editing the Form

You can use the inline XAML editor to adjust properties of controls and add new ones. 

### Setting Control Properties

You can use the Property window to set properties of a control. To do so, select the control you'd like to modify and then set the specified property in the Property window. The designer and XAML will update after you press `Enter` . 

![Setting Properties of a Window](../.gitbook/assets/properties.gif)



## Options

### Context Menu

Add an Open with PSScriptPad context menu item to Windows Explorer so you can right click on PS1 files and open them in the editor.

### Font Size

Set the font size for the terminal and code editor windows.

### Override Execution Policy

Set the execution policy for PSScriptPad to Bypass.

### Themes

You can switch between dark and light themes using the options dialog. 

![](../.gitbook/assets/image%20%2828%29.png)





