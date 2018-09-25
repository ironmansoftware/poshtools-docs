## Build Events

[_Visual Studio 2015_](https://poshtools.com/docs/poshtools-docs/enabling-msbuild-support-visual-studio-2015-powershell-projects/)_requires a manual step in order to take advantage of build events. _

PowerShell Projects support pre-build and post-build events. Currently, there is no actually build step so running pre-build will simply run a script before the post-build script.

You can access the pre and post build events by opening the Properties page for you project. You can add PowerShell scripts and access MSBuild variables in your build events. You build events are executed when MSBuild builds your PowerShell project.

![](https://i2.wp.com/poshtools.com/wp-content/uploads/2017/06/buildevents.png?resize=567%2C472&ssl=1)

