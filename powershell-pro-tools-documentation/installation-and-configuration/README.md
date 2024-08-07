# Installation and Licensing

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

### Installing Previous Versions

#### Visual Studio

Previous versions of the Visual Studio extension can be found on our [downloads page.](https://ironmansoftware.com/downloads)

![](<../../.gitbook/assets/image (61).png>)

#### Visual Studio Code

You can select from previous versions of the Visual Studio Code extension in the extension pane. Click the Gear icon next to PowerShell Pro Tools and select Install Another Version...

![](<../../.gitbook/assets/image (60).png>)

#### PowerShell Module

You can install a previous version of the PowerShell Module by using the `-RequiredVersion` parameter of `Install-Module`.

```
Install-Module -Name PowerShellProTools -RequiredVersion 5.7.0
```

## Licensing

{% hint style="warning" %}
We are sunsetting PowerShell Pro Tools. End of sales will be October 1st, 2024 with end of life is October 1st, 2025. [Learn more](https://blog.ironmansoftware.com/powershell-pro-tools-end-of-life).
{% endhint %}

### Trial Licenses

By default, PowerShell Pro Tools installs and allows for a limited set of features. If you would like to trial PowerShell Pro Tools without these limitations, you can [request a trial key](https://www.ironmansoftware.com/trial/powershell-pro-tools).&#x20;

### Purchasing a License

Visit the [purchasing page](https://www.ironmansoftware.com/pricing/powershell-pro-tools) and follow the instructions to purchase a license. A license will be emailed to you within ten minutes of purchase.&#x20;

### Installing a License

### Visual Studio&#x20;

PowerShell Tools for Visual Studio does not require a license.

### Visual Studio Code

PowerShell Pro Tools for Visual Studio Code does not require a license.

### Manual Installation

You can manually install your license by placing a `license.lic` file in your `%AppData%\PowerShell Pro Tools` directory. The directory may not exist. Place the full XML of the license file you received in this file.&#x20;

### PSScriptPad&#x20;

PSScriptPad licenses can be installed using the above methods. PSScriptPad also supports loading license files that reside next to the PSScriptPad.exe file. Create a file called `license.lic` and place it in the same directory as PSScriptPad. The license will be loaded from this location, if present.&#x20;
