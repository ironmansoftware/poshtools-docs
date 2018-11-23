# Profiler

PowerShell Pro Tools offers a script performance profiler to time the execution of your script. It helps to locate slow sections of code and provides the number of times particular lines are called. 

The feature is best defined as an instrumentation profiler that injects cmdlet calls into your script to thoroughly analyze your script. The script is executed with this injected code to accurately time the pipelines within your script. 

## Requirements

To use the profiler, you will need the PowerShell Pro Tools [Visual Studio Code Extension](https://marketplace.visualstudio.com/items?itemName=ironmansoftware.powershellprotools) and [module](https://www.powershellgallery.com/packages/PowerShellProTools/1.10.0). Currently, the module is only available on Windows. 

## Profiling a Script

To profile a script, open the script you wish to profile and execute the `PowerShell: Profile Script` command from within VS Code \(Ctrl+Shift+P\). The script will be instrumented and then executed within the VS Code PowerShell Session. After execution is complete, script timings will be added directly to the editor on the lines in which they were recorded. 

![Profiler information](../.gitbook/assets/image%20%284%29.png)

The profile information will remain in the editor until you execute the `PowerShell: Clear Profiling Information` command in VS Code. 

### Limitations <a id="limitations"></a>

Being an early version of the profiler, there are some limitations.

#### **Single Script Support** <a id="single-script-support"></a>

The profiler only profiles the current script. It will not profile scripts or modules that you reference. If you use functions within pipelines in your profiled script, those functions will be timed but their internal operations will not.

Hot Path Support

Although the hot path information is available in the output from the profiler, there is no visual representation of this information.

#### Pipeline Element Timing <a id="pipeline-element-timing"></a>

The profiler has early support for pipeline element timing but does not expose this in this version. For example, a pipeline like the one below will result in a single timing even though multiple commands are being called.

```text
Get-Process | Select-Object Name | Out-String  40.85% (1 calls)
```

In a future version, individual commands will be able to be profiled.

