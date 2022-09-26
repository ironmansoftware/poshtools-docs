# Visual Studio Offline Installation

You can accomplish offline installation by following the [Visual Studio offline installation instructions](https://docs.microsoft.com/en-us/visualstudio/install/create-an-offline-installation-of-visual-studio?view=vs-2019#use-the-command-line-to-create-a-local-cache).&#x20;

Download the Visual Studio Edition of choice and run the following command line.&#x20;

```
 vs_community.exe --layout c:\vslayout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US
```

You will now need to [download the PowerShell Tools VSIX](https://marketplace.visualstudio.com/items?itemName=AdamRDriscoll.PowerShellToolsforVisualStudio2017-18561) file from the Visual Studio Marketplace.&#x20;

On a machine with an internet connection, double click the VSIX file.

![](<../../.gitbook/assets/image (23).png>)

The online machine will install the certificate to the local machine.  After the VSIX installer opens, click the Digital Signature link to view more information about the certificate. Click Install Certificate.

![](<../../.gitbook/assets/image (16).png>)

Next, you'll want to export the certificate to a file. Use certmgr.msc to export the certificate.

![](<../../.gitbook/assets/image (18).png>)

Ensure you export all the certificates in the certificate path. &#x20;

![](<../../.gitbook/assets/image (8) (2).png>)

Move the P7B file to the offline machine along with the PowerShell Tools VSIX file. Install the certificate to the certificate store.&#x20;

After creating the offline installation layout, you can then move the `vslayout` folder to an offline location.  Within the certificates folder within `vslayout` folder, you may need to [install all the certificates ](https://docs.microsoft.com/en-us/visualstudio/install/install-certificates-for-visual-studio-offline?view=vs-2019)in order to correctly install the package.&#x20;

Run the offline installation using the following command line.

```
C:\vslayout\vs_community.exe --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional
```

Finally, double click the PowerShell Tools VSIX to install PowerShell Tools for Visual Studio.&#x20;
