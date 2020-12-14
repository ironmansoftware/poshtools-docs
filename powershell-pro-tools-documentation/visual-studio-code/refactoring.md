---
description: Refactoring commands for VS Code.
---

# Refactoring

{% hint style="warning" %}
This functionality is coming in a future version of PowerShell Pro Tools.
{% endhint %}

## About

Refactorings allow you to change or generate code based on the code you have. You will find a list of refactorings below. You can invoke a refactor by invoke the Refactor command or by pressing the key binding `Ctrl+Alt+R` . 

Only valid refactorings will be returned in the drop down menu.

## Convert to Splat

Converts a command invocation into a splatting expression and creates a hashtable named `$Parameters` and then passes that hashtable as a splatting expression to the command. Positional arguments are not added to the hashtable.

![Convert to Splat](../../.gitbook/assets/convert-to-splat.gif)

## Export Module Member

Exports the selected variable or function from a module using `Export-ModuleMember`.

![Export Module Member](../../.gitbook/assets/export-module-member.gif)

## Extract Selection to File

You can use the Extract Selection to File refactoring to create a new file based on the selection in the current active editor. 

![Extract Selection to File](../../.gitbook/assets/extract-file%20%281%29.gif)

