## Packaging in Visual Studio Code

Since [Merge-Script](https://poshtools.com/docs/posh-pro-tools/merge-script/) can be called from the task integration in Visual Studio Code, it’s very easy to create a task.json file that packages scripts by using Ctrl+Shift+B. You can define the task.json like this.

`{`

`    "version": "0.1.0",`

`    "tasks": [`

`        {`

`            "taskName": "build",`

`            "command": "powershell",`

`            "args": ["Merge-Script -Script '${file}' -Bundle -OutputPath '${fileDirname}\\out' -OutputType Executable"],`

`            "isBuildCommand": true,`

`            "showOutput": "silent"`

`        }`

`    ]`

`}`

From VS Code, you can simply open a PS1 file and press the key combination Ctrl+Shift+B. The output of the command will be written to a “out” folder in the same directory as the PS1 file you are building.

