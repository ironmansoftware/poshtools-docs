---
description: Changelog for PowerShell Protect
---

# PowerShell Protect

## 2022.9.0 - 9/13/2022

* Fixed an issue where not all formats of Invoke-Expression would be detected with the built in rule.&#x20;

## 2022.7.0 - 7/12/2022

* Fixed an issue where license files were not correctly validated

## 2022.6.0 - 6/14/2022

* Added support to PowerShell Universal for generating PowerShell Protect configuration files
* Added support for sending events to PowerShell Universal&#x20;

## 2021.12.1 - 12/15/2021

* Built-in rules no longer require a license.&#x20;

## 2021.12.0 - 12/14/2021

* Improved error logging for failed conditions
* Fixed an issue where invalid configurations would cause exceptions in built-in rules
* Added support for Application Hash (SHA256) conditions
* Added support for Assembly conditions
* Added support for Assembly Hash (SHA256) conditions
* Added support for specifying a license within the configuration file
* Added support for matching any condition on a rule
* Fixed an issue where you could specify -Format for -Tcp or -UDP on New-PSPAction
* Added built-in detection for attempts to explore Log4j CVE-2021-44228

## 2021.9.0 - 9/14/2021

* Added support for sending event log actions based on rules

## 2.3.1 - 4/21/2021

* Added subscription activation caching to prevent excessive web requests

## 2.3 - 4/19/2021

* Added support for disabling individual rules with `-DisabledBuiltinConditions`
* PowerShell Protect is now a part of PowerShell Pro Tools.
