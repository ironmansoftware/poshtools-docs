# Visual Studio Offline Installation

You can accomplish offline installation by following the [Visual Studio offline installation instructions](https://docs.microsoft.com/en-us/visualstudio/install/create-an-offline-installation-of-visual-studio?view=vs-2019#use-the-command-line-to-create-a-local-cache). 

Download the Visual Studio Edition of choice and run the following command line. 

```text
 vs_community.exe --layout c:\vslayout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US
```

You will now need to [download the PowerShell Tools VSIX](https://marketplace.visualstudio.com/items?itemName=AdamRDriscoll.PowerShellToolsforVisualStudio2017-18561) file from the Visual Studio Marketplace. 

On a machine with an internet connection, double click the VSIX file.

![](../../.gitbook/assets/image%20%2822%29.png)

The online machine will install the certificate to the local machine.  After the VSIX installer opens, click the Digital Signature link to view more information about the certificate. 

![](../../.gitbook/assets/image%20%2816%29.png)

Next, you'll want to export the certificate to a file. Use certmgr.msc to export the certificate.

![](../../.gitbook/assets/image%20%2818%29.png)

Ensure you export all the certificates in the certificate path.  

![](../../.gitbook/assets/image%20%288%29.png)

Move the P7B file to the offline machine along with the PowerShell Tools VSIX file. Install the certificate to the certificate store. 

After creating the offline installation layout, you can then move the `vslayout` folder to an offline location.  Within the certificates folder within `vslayout` folder, you may need to [install all the certificates ](https://docs.microsoft.com/en-us/visualstudio/install/install-certificates-for-visual-studio-offline?view=vs-2019)in order to correctly install the package. 

Run the offline installation using the following command line.

```text
C:\vslayout\vs_community.exe --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional
```

Finally, double click the PowerShell Tools VSIX to install PowerShell Tools for Visual Studio. 

