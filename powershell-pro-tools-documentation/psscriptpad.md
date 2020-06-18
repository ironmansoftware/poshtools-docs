# PSScriptPad

PSScriptPad is the tiny editor for Windows PowerShell. It requires no installation or configuration. It weighs in around 4Mbs, can editor and execute PowerShell scripts, design Windows Forms and Package Executables. 

## Download

You can download PSScriptPad from our website. It is just a .exe file. 

{% embed url="https://ironmansoftware.com/psscriptpad/" %}

## Opening PSScriptPad

PSScriptPad can just be opened by double clicking the PSScriptPad.exe. 

You can also open PSScriptPad if you have the PowerShell Pro Tools module installed. 

```text
Show-PSScriptPad 
```

You can also use the `pad` alias. 

```text
pad .\test.ps1
```

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

## PSReadline

PSScriptPad supports [PSReadline](https://github.com/PowerShell/PSReadLine). PSReadline is packaged into the PSScriptPad executable and there is no need to install it separately. 



