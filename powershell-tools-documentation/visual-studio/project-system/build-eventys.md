# Build Events

PowerShell Projects support pre-build and post-build events. Currently, there is no actual build step so running pre-build will simply run a script before the post-build script.

![](<../../../.gitbook/assets/image (82).png>)

You can access the pre and post build events by opening the Properties page for you project. Right click on your project within the Solution Explorer window and select Properties. You can add PowerShell scripts and access MSBuild variables in your build events. You build events are executed when MSBuild builds your PowerShell project.

![Project Properties](<../../../.gitbook/assets/image (83).png>)
