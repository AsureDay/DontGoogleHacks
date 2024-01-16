# DontGoogleHacks
Some hacks for fast develop

## Python CPP debugger 
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
* `echo 0 | sudo tee /proc/sys/kernel/yama/ptrace_scope` чтобы не было постояного запроса прав суперюзера
* не забыть компилировать файл в режиме Debug

## быстрое создание python venv 
* `pip install virtualenv && virtualenv venv --python=python3.8`

## CUDA 
* тут пока не будет подробной инструкции, но важно не забывать добавлять в bashrc 

```bash
export MYPYTHONPATH="" # вставить python
export LD_LIBRARY_PATH=/usr/local/cuda-11.8/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
export PATH=/usr/local/cuda-11.8/bin${PATH:+:${PATH}}
CUDNN_PATH=${MYPYTHONPATH}/python3.8/site-packages/nvidia/cudnn
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$CONDA_PREFIX/lib/:$CUDNN_PATH/lib
``` 
