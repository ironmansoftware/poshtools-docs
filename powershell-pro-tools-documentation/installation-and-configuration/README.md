# Installation and Licensing

## Installation

### **Visual Studio**

PowerShell Pro Tools is included with [PowerShell Tools for Visual Studio](https://marketplace.visualstudio.com/items?itemName=AdamRDriscoll.PowerShellToolsforVisualStudio2017-18561). You can install it through Visual Studio or download it from the Marketplace.&#x20;

For offline installation instructions, click here.

### **Visual Studio Code**&#x20;

The Visual Studio Code extension is available on the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ironmansoftware.powershellprotools) and can be installed from within Visual Studio Code. Search for PowerShell Pro Tools when searching in VSC.&#x20;

### **Visual Studio Code Offline Install**

You can install a Visual Studio Code extension by downloading the VSIX file from the Marketplace and then clicking Install from VSIX within the extension pane in Visual Studio Code.&#x20;

![](<../../.gitbook/assets/image (29).png>)

![](<../../.gitbook/assets/image (30).png>)

You will also need to install the proper binaries for your environment. You can download the binaries using the following PowerShell script on an internet connected machine. You will need to ensure you download the matching version of the binaries.

```
$Version = '2021.12.1'
Invoke-WebRequest "https://imsreleases.blob.core.windows.net/vscode/windows.$Version.zip" -OutFile .\vscode.zip
```

Once downloaded, you will need to transfer the ZIP to the offline machine. The ZIP needs to be extracted to your user's home directory. Ensure that the proper version is included.

```
$TargetDir = "$ENV:UserProfile\PowerShellProTools\2021.12.1\windows"
Expand-Archive .\vscode.zip -Destination $TargetDir
Get-ChildItem $TargetDir -Recurse | Unblock-File 
```

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

### Trial Licenses

By default, PowerShell Pro Tools installs and allows for a limited set of features. If you would like to trial PowerShell Pro Tools without these limitations, you can [request a trial key](https://www.ironmansoftware.com/trial/powershell-pro-tools).&#x20;

### Purchasing a License

Visit the [purchasing page](https://www.ironmansoftware.com/pricing/powershell-pro-tools) and follow the instructions to purchase a license. A license will be emailed to you within ten minutes of purchase.&#x20;

### Installing a License

### Visual Studio&#x20;

You can install your license file in Visual Studio by clicking View \ PowerShell \ Settings and navigating to the settings tab.&#x20;

![](<../../.gitbook/assets/license (1).gif>)

#### Visual Studio Code

When the PowerShell Pro Tools extension activates, it will ask for a license key. You can click Install License to install the license key.

![](../../.gitbook/assets/install-license.gif)

Use the `PowerShell Pro Tools: Install License Key` command to install your license.&#x20;

In Visual Studio Code, press `Ctrl+Shift+P` to activate the command palette. Once the palette is shown, you can start to search for the command listed above. Select it and press enter. Paste the entire contents of the license key file into the input box shown.

![](../../.gitbook/assets/install-license-full.gif)

### PowerShell

You can use the `Install-PoshProToolsLicense` cmdlet to install your license.

```
Install-PoshProToolsLicense -Path C:\license.txt
```

### Manual Installation

You can manually install your license by placing a `license.lic` file in your `%AppData%\PowerShell Pro Tools` directory. The directory may not exist. Place the full XML of the license file you received in this file.&#x20;

### PSScriptPad&#x20;

PSScriptPad licenses can be installed using the above methods. PSScriptPad also supports loading license files that reside next to the PSScriptPad.exe file. Create a file called `license.lic` and place it in the same directory as PSScriptPad. The license will be loaded from this location, if present.&#x20;
