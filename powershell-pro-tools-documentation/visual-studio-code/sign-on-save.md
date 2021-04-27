---
description: Sign scripts after they are saved.
---

# Sign On Save

The Sign on Save features provides a way to sign scripts right after they are saved using a configured code-signing certificate. 

## Configuring Sign On Save

You can configure sign on save by enabling the feature in settings and providing a certificate path.

![](../../.gitbook/assets/image%20%2866%29.png)

The path can be left empty and the extension will provide a quick pick drop down the first time you save a file. 

![](../../.gitbook/assets/image%20%2854%29.png)

Once you select a certificate, it will store that in the Sign On Save Certificate setting. You'll notice the setting is the full path to the certificate in the certificate store. 

```text
Microsoft.PowerShell.Security\Certificate::CurrentUser\My\Aasdfasdf23fdasfd0as872389723soad
```

With the setting enabled, any time you save a file, `Set-AuthenticodeSignature` will be called and your file will be signed. 

