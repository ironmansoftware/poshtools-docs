## Unit Test Adapter

## Getting Started

The PowerShell Tools for Visual Studio integrates a unit test adapter that can discover and execute[Pester](https://github.com/pester/Pester)tests. To write tests you will need to create a PS1 file that ends in the extension “Tests.PS1”. The test adapter will only look in files with this extension. From there, you can author Pester tests as you normally would. The Test Explorer window will display the tests it finds and you can execute them by clicking Run All or Run.

Test results are shown just like any other testing framework. They will include the result of the test, the reason for failure and a stack trace to the offending code that has failed.

## Pester Installation

The test adapter will look in a few places while attempting to load the Pester module.

1. Test run directory
2. Solution Package directory
   _Note: this does not follow the NuGet package resolution logic and only currently uses the solution directory_
3. PSModule path

## Debugging Issues with the test adapter

The test adapater will log to the Output pane in the Tests category. Check here first for any issues you may encounter when writing tests.

