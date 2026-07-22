# Troubleshooting

* Use `-Verbose` on `New-Installer` to see WiX compiler and linker output.
* Verify every file referenced by `New-InstallerFile`, `AddRemoveProgramsIcon`, shortcut icons, and UI parameters exists before building.
* Keep file and directory IDs unique when you specify them manually.
* Use a stable `UpgradeCode` and increase `Version` for upgrade releases.
* Use `-RequiresElevation` for installers that write to protected machine locations such as Program Files.
* Inspect the generated `.wxs` file when WiX reports validation or linking errors.
