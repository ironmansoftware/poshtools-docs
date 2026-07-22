# Installer Identity

`New-Installer` defines the MSI package and runs the WiX build. These parameters are the ones you will usually set first.

* `ProductName` is required and appears in the installer and Add/Remove Programs.
* `UpgradeCode` is required. Generate it once for a product and keep it the same for every release of that product.
* `Version` defaults to `1.0`. Increase it when shipping upgrades. Windows Installer blocks downgrades.
* `ProductId` defaults to `*`, which lets Windows Installer generate a new product code for the package.
* `Manufacturer` defaults to `Ironman Software, LLC`; set it to your organization for published installers.
* `OutputDirectory` is required and receives the MSI and WiX build artifacts.
* `Platform` defaults to `x86` and accepts `x86`, `x64`, `ia64`, `arm`, `intel`, or `intel64`.
* `Description`, `HelpLink`, `AboutLink`, and `AddRemoveProgramsIcon` add installer metadata.

Generate an upgrade code once and store it in your build script or build configuration.

```powershell
New-Guid
```

Do not call `New-Guid` inside the installer build for `UpgradeCode` after your first release. Changing the upgrade code makes Windows Installer treat the MSI as a different product.
