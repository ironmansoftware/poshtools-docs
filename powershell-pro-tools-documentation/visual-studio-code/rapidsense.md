---
description: High performance statement completion.
---

# RapidSense

![RapidSense](../../.gitbook/assets/rapidsense\_small.png)

RapidSense is an alternative to the default PowerShell IntelliSense that provides high performance, customizable statement completion. It aggressively caches PowerShell elements to provide to the best performance possible. It sacrifices some of the features of IntelliSense to provide this performance but aims to provide the most common statement completion suggestions. You can quickly toggle between IntelliSense and RapidSense.&#x20;

RapidSense works with Windows PowerShell and PowerShell 7.

{% embed url="https://youtu.be/rIp6VPh91h0" %}



## Enabling RapidSense

To enable RapidSense, click the IntelliSense button on the status bar.&#x20;

![](<../../.gitbook/assets/image (48).png>)

After clicking the IntelliSense button, it will toggle to RapidSense. RapidSense will begin the caching problem. It should only take a couple of seconds.&#x20;

![](<../../.gitbook/assets/image (53).png>)

## Using RapidSense

![](<../../.gitbook/assets/image (50).png>)

RapidSense works the same as IntelliSense. As you begin typing, it will suggest commands, parameters, variables, properties, methods, paths and types. RapidSense currently does not complete static members, classes, or attributes.&#x20;

RapidSense triggers on on the following characters:&#x20;

```
,
.
-
[
\
```

When a trigger character is pressed the standard statement completion UI will be shown.&#x20;

![](<../../.gitbook/assets/image (47) (1) (1).png>)

## Configuring RapidSense

RapidSense can be configured to ignore certain assemblies, types, modules and commands. You can change these settings in the VS Code settings UI.&#x20;

For each of the ignored elements, you can define an array and separate them with semicolons. Each segment is treated as a regular expression.

For example, if you wanted to prevent cmdlets in the `ActiveDirectory` module from showing in RapidSense, add the following to the Ignored Modules setting.

```
ActiveDirectory
```

If you wanted to exclude all `System` assemblies from type completion. You could add a regular expression to the Ignore Assemblies setting.

```
System.*
```

You can still use these commands in your scripts but they will not be suggested to you are you type. Ignoring elements improves performance because they are not included in the cache at all. Including many ignored elements may reduce performance of the recaching process as it need to process additional regular expressions across the elements. Recaching happens after executing the debugger.

### Available Settings

**Ignored Assemblies** - Ignore types in certain assemblies \
**Ignored Types** - Ignore specific types\
**Ignore Modules** - Ignore commands found in certain modules\
**Ignore Commands** - Ignore specific commands\
**Ignore Variables **- Ignore specific variables.

## Disabling RapidSense

You can toggle back to standard IntelliSense by click the RapidSense button in the status bar. RapidSense caches will not be recached when RapidSense is disabled.&#x20;

![](<../../.gitbook/assets/image (52).png>)



