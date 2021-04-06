---
description: Changelog for PSCommander.
---

# PSCommander

## 1.1.1 - 4-6-2021

### Changed

* Code signed the PSCommander module
* Fixed an issue where PSCommander could fail to load

## 1.1.0 - 4-5-2021

### Added

* Added -Icon to New-CommanderToolbarIcon for customizing the icon
* Added Register-CommanderEvent for handling events that happen within commander.
* Added -ArgumentList to New-CommanderMenuItem to easily pass arguments to the Action script block.
* Added -ConfigFilePath to Start-Commander

### Changed

* Fixed an issue where launching Edit Config would not work when installed to a path with a space

## 1.0.2 - 3-28-2021

Bugs Fixed

* Cannot reapply hotkeys 
* Menu doesn't show up at all if you don't do toolbar icon 
* If you remove toolbar icon it continues showing the previous version 
* Open config the first time when there is no config 
* Executing cmdlets in regular PS instance doesn't work 
* Install-CommanderLicense not exposed in PSD1
* New-CommanderSchedule not exposed in PSD1

## 1.0.1 - 3-27-2021

Initial release 

