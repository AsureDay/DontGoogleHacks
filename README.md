# DontGoogleHacks
Some hacks for fast develop

# Python CPP debugger 
* `launch.json`
```json
    {
      "name": "Python: Current File",
      "type": "python",
      "request": "launch",
      "program": "${file}",
      "console": "integratedTerminal",
    },
    {
      "name": "Python C++ Debugger",
      "type": "pythoncpp",
      "request": "launch",
      "pythonLaunchName": "Python: Current File",
      "cppAttachName": "(gdb) Attach",
      // "preLaunchTask": "debug build cpp files"
    },
    {
      "name": "(gdb) Attach",
      "type": "cppdbg",
      "request": "attach",
      "program": "PATH TO PYTHON",
      "processId": "",
      "MIMode": "gdb",
      "setupCommands": [
          {
              "description": "Enable pretty-printing for gdb",
              "text": "-enable-pretty-printing",
              "ignoreFailures": true
            }
      ]
        //   "postDebugTask": "Enable ptrace_scope",
        //   "preLaunchTask": "Disable ptrace_scope",
    },

```
* не забыть компилировать файл в режиме Debug

