# Installation and Licensing

### Installation

**Visual Studio**

PowerShell Pro Tools is included with [PowerShell Tools for Visual Studio](https://marketplace.visualstudio.com/items?itemName=AdamRDriscoll.PowerShellToolsforVisualStudio2017-18561). You can install it through Visual Studio or download it from the Marketplace. 

For offline installation instructions, click here.

**Visual Studio Code** 

The Visual Studio Code extension is available on the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ironmansoftware.powershellprotools) and can be installed from within Visual Studio Code. Search for PowerShell Pro Tools when searching in VSC. 

**Visual Studio Code Offline Install**

You can install a Visual Studio Code extension by downloading the VSIX file from the Marketplace and then clicking Install from VSIX within the extension pane in Visual Studio Code. 

![](../../.gitbook/assets/image%20%2829%29.png)

![](../../.gitbook/assets/image%20%2830%29.png)



**PowerShell Module**

The PowerShell Module is available on the [PowerShell Gallery](https://www.powershellgallery.com/packages/powershellprotools/1.3.0). 

## Licensing

### Trial Licenses

By default, PowerShell Pro Tools installs and allows for a limited set of features. If you would like to trial PowerShell Pro Tools without these limitations, you can [request a trial key](https://ironmansoftware.com/product/powershell-pro-tools-trial/). 

### Purchasing a License

Visit the [purchasing page](https://ironmansoftware.com/powershell-pro-tools/) and follow the instructions to purchase a license. A license will be emailed to you within ten minutes of purchase. 

### Installing a License

### Visual Studio 

Click Help and About PowerShell Pro Tools to view and change your license.

#### Visual Studio Code

Use the `PowerShell Pro Tools: Install License Key` command to install your license. Simply copy and paste the contents of your license in to the text box that appears. You can access the commands by using the `Ctrl+Shift+P` key stroke. 

### PowerShell

You can use the `Install-PoshProToolsLicense` cmdlet to install your license.

```text
Install-PoshProToolsLicense -Path C:\license.txt
```

### Manual Installation

You can manually install your license by placing a `license.lic` file in your `%AppData%\PowerShell Pro Tools` directory. The directory may not exist. Place the full XML of the license file you received in this file. 

