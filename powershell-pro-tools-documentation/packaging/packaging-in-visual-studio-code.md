# Packaging in Visual Studio Code

{% hint style="info" %}
Requires [PowerShell Pro Tools](https://ironmansoftware.com/poshtools)
{% endhint %}

PowerShell Pro Tools provides an [extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ironmansoftware.powershellprotools). The VSC extension relies on the [PowerShell Pro Tools](https://www.powershellgallery.com/packages/powershellprotools/1.3.0) module to be installed. If it is not installed, the VSC extension will install it automatically. 

Once installed in VS Code, you can execute the `PowerShell: Package as Executable` command. This command will package the current PS1 script into and executable using `Merge-Script`. 

Additionally, a `package.psd1` file will be created to allow for greater control over the options available when packaging via `Merge-Script`. For more information on the settings available in the `package.psd1` file, check out the [documentation here](https://docs.poshtools.com/powershell-pro-tools-documentation/powershell-module/aboutmergescriptconfig).

