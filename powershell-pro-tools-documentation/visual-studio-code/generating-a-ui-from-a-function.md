# Generating a UI from a function

With the PowerShell Pro Tools VS Code extension, you can convert a PowerShell function into a Windows Form app without using the form designer at all. To this, you'll want to start with a PS1 file with a single function defined within it.&#x20;

```
function New-User {
    param([String]$UserName, [Switch]$Enabled, [ValidateSet("Administrator", "IT", "HR")]$Department)
}
```

In VS Code, open the PS1 file you'd like to make a UI out of. Then open the command palette with `Ctrl+Shift+P` and search for `PowerShell: Generate Windows Form`.&#x20;

Once you select that, two new files will be created. One will include `form.ps1` and another will include `form.designer.ps1`.&#x20;

If you execute the `form.ps1` file, your UI will be shown.&#x20;

![Auto-generated UI](<../../.gitbook/assets/image (5) (1).png>)
