# Generate a Tool from a Function

Using the `PowerShell Pro Tools: Generate Tool` command you can generate a WinForm and then compile it into an executable in one step. It uses the same concept as the Generate a UI from a function and the PoshTools packager to create the tool.

Press `Ctrl+Shift+P` to open the command pallete and search for the command. You will need to have a PS1 file open with a single function in it that defines the parameters for the tool you'd like to create.&#x20;

For example, you could have a new user function like this.&#x20;

```
function New-User {
    param([String]$UserName, [Switch]$Enabled, [ValidateSet("Administrator", "IT", "HR")]$Department)
}
```

This would generate a form that looked like this.&#x20;

![Auto-generated UI](<../../.gitbook/assets/image (5) (1).png>)

If the file was named `NewUser.ps1` , then a `NewUser.exe` would be created that would show the form and execute your tool.&#x20;
