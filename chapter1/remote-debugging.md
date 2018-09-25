# Remote Debugging

Remote process debugging is now supported! You can use this feature to attach and debug any PowerShell host process, exactly the same as you would with a normal PowerShell console.

## Remote Attaching

### Difference between Remote Attaching and Remote Session

Remote Debugging is a totally new and separate feature from the already existing Remote Session feature. If you are wanting to debug an already running process that is say stuck in a loop or producing odd log data, then you can now Remote Debug it. By doing so, you are not required to actually stop the process. Remote Session on the other hand is simply starting/executing a script on a remote machine from Visual Studio.

### Remote Attaching Prerequisites

* Your local machine \(the one running Visual Studio\) must have PowerShell v4 or higher installed
* Your remote machine \(the one running the remote process\) must have PowerShell v5 or higher installed
* If your remote machine has a PowerShell version lower than 5.0.10240.0, then the remote process must be run as administrator. This is a bug with earlier versions of the PowerShell 5 preview.

### Attaching to a Remote Process

Before attaching to a remote process, you will need to know the name or address of your machine, such as:

> some.machine.net

Next, you will need to know whether or not your machine requires you to connect with a secure \(SSL\) connection. If it does, you will need to install the SSL certificate of your remote machine before continuing \(see Remote Attaching with Azure below for more information\). Finally, you will need to know the port number your remote machine uses for PowerShell sessions. By default, PowerShell and PowerShell Tools attempt to connect to 5985 for non-SSL connections and 5986 for SSL connections. If your port is different you can simply add it to the end of your machine name/address as so:

> some.machine.net:5988

You can now open up Visual Studio and go to Debug -&gt; Attach to Process, and then select the appropriate PowerShell Tools remote debugging transport from the transport dropdown. Which one you choose will depend on whether or not you need to use SSL. Once you have chosen a transport, enter in your machine name \(and port if needed\) as the qualifier and then hit refresh. You will now be prompted to login:

![](https://camo.githubusercontent.com/8c167068e8bd25878adff1b1244d16d208094e1f/687474703a2f2f692e696d6775722e636f6d2f476166493575692e706e67)

You’ll need to login with either a[username@domain.com](mailto:username@domain.com)format or domain\username format. If your machine doesn’t have a domain, you can simply use MachineName\username to login. For example, if your machine name is poshtools and your username is Matthew:

![](https://camo.githubusercontent.com/fae69c56104b3184758c93728352081ca5f29a25/687474703a2f2f692e696d6775722e636f6d2f38436b347438472e706e67)

Once you have entered your credentials hit OK. Your window should now look something like this:

![](https://camo.githubusercontent.com/11f299ef07de8817f48fd3d9631b19211de8d16b/687474703a2f2f692e696d6775722e636f6d2f4b6747767854422e706e67)

If for some reason you don’t see your process, make sure you are running it as administrator if you have a PowerShell version lower than 5.0.10240.0. You may also not have the rights to debug the process depending on who started it.

If you do see your process, then go ahead and hit attach. The process you selected will now be attached to and the script that it was running copied over to your local machine.

![](https://camo.githubusercontent.com/cf045c94657f589799a7dc700cb7f1bd12ebf532/687474703a2f2f692e696d6775722e636f6d2f784733764a47362e706e67)

You have now successfully attached to the remote process. From here you can set and remove breakpoints, step into, step over, step out, view the call stack, the locals window, and execute commands in the PowerShell Tools Interactive Window \(edit and continue, variable examination, etc.\).

Once you have finished debugging, you may complete your session by hitting the Stop Debugging button.

A final few things to note about remote attaching:

* Stepping into external files is currently not supported.
* If you stop/detach while the script is running any set breakpoints may not be cleared from the remote program which could cause it to stop in the future.
* If you have a copy of the remote script open before you attach, set breakpoints and then attach, those breakpoints will not be transferred over to the remote program.
* Issuing debugging cmdlets in the interactive window while attached to a process is not fully supported.
* You should not be using remote attaching to debug a local process. You should use local attaching to attach to a local process \(see below\).

### Remote Attaching with Azure

Attaching to a remote process running on Azure is just as easy as attaching to a process running on any other machine. The first thing you will need to do is install the SSL certificate from your Azure machine onto your local computer. You can follow the first half of[this MSDN blog post](http://blogs.msdn.com/b/sriharsha/archive/2013/10/26/remote-powershell-in-azure-iaas-virtual-machines.aspx)for instructions on how to do so. Once you have installed the certificate, simply follow the steps above on how to remote attach. Remember, if you have configured your machine to have a SSL port other than 5986 you will need to specify it in your qualifier.

## Local Debugging

### Local Debugging Prerequisites

* Your machine must have PowerShell v5 or higher installed

### Attaching to a Local Process

To attach to a local process, go to Debug -&gt; Attach to Process, and then make sure that the Default transport option is selected. You will then need to make sure that the “Attach to:” type is only PowerShell code:

![](https://camo.githubusercontent.com/d0343f6b1ae7c85f939d1fd3c4beea6d286d04ec/687474703a2f2f692e696d6775722e636f6d2f346758354c6d452e706e67)

You may then scroll down the list of running processes to find the one you want to attach to. In most cases, you will probably be looking for powershell.exe, but other processes are attachable. Once you find it, select it and hit attach.

![](https://camo.githubusercontent.com/b05959abb268589356db46687ac618184741d498/687474703a2f2f692e696d6775722e636f6d2f6b4b31373855552e706e67)

If you are unsure as to whether or not you can attach to a process, simply look for the PowerShell Debug Engine in the Type column of the process.

![](https://camo.githubusercontent.com/8c1ad2c36c60bc46cc2d8983016a2fa058437abc/687474703a2f2f692e696d6775722e636f6d2f4c76484e4132342e706e67)

You will now be attached to the selected program and the running script opened in Visual Studio. Similar to remote attaching, you can set and remove breakpoints, step into, step over, step out, view the call stack, the locals window, and execute commands in the PowerShell Tools Interactive Window \(edit and continue, variable examination, etc.\). Once you have finished debugging, you may complete your session by hitting the Stop Debugging button.

A final few things to note about remote debugging:

* If you stop/detach while the script is running, any set breakpoints may not be cleared from the remote program which could cause it to stop in the future.
* If you have a copy of the script open before you attach, set breakpoints and then attach, those breakpoints will not be transferred over to the remote program.
* Issuing debugging cmdlets in the interactive window while attached to a process might produce negative behavior.
* Attaching directly to the PowerShell Tools Host process is not fully supported.
* If you are running PowerShell tools in 32 bit mode, the ability to attach to a 64 bit process is not yet supported



