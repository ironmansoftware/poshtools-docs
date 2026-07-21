# Installation

Installation

### **Visual Studio**

PowerShell Pro Tools is included with [PowerShell Tools for Visual Studio](https://marketplace.visualstudio.com/items?itemName=AdamRDriscoll.PowerShellToolsforVisualStudio2017-18561). You can install it through Visual Studio or download it from the Marketplace.&#x20;

For offline installation instructions, click here.

### **Visual Studio Code**&#x20;

The Visual Studio Code extension is available on the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ironmansoftware.powershellprotools) and can be installed from within Visual Studio Code. Search for PowerShell Pro Tools when searching in VSC.&#x20;

### **Visual Studio Code Offline Install**

You can install a Visual Studio Code extension by downloading the VSIX file from the Marketplace and then clicking Install from VSIX within the extension pane in Visual Studio Code.&#x20;

![](<../../.gitbook/assets/image (29).png>)

![](<../../.gitbook/assets/image (30).png>)

**PowerShell Module**

The PowerShell Module is available on the [PowerShell Gallery](https://www.powershellgallery.com/packages/powershellprotools/1.3.0).&#x20;

#### Visual Studio Code

You can select from previous versions of the Visual Studio Code extension in the extension pane. Click the Gear icon next to PowerShell Pro Tools and select Install Another Version...

![](<../../.gitbook/assets/image (60).png>)

#### PowerShell Module

You can install a previous version of the PowerShell Module by using the `-RequiredVersion` parameter of `Install-Module`.

```
Install-Module -Name PowerShellProTools -RequiredVersion 5.7.0
```
