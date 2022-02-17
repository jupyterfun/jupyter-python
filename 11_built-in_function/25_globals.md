## globals() 返回全局变量字典

内置函数 globals()，Python 官方文档描述如下：


```python
help(globals)
```

    Help on built-in function globals in module builtins:
    
    globals()
        Return the dictionary containing the current scope's global variables.
        
        NOTE: Updates to this dictionary *will* affect name lookups in the current
        global scope and vice-versa.
    
    

返回包含当前作用域的全局变量字典。这总是当前模块的字典（在函数或方法中，不是调用它的模块，而是定义它的模块）。

更新此字典 *将* 影响当前全局范围内的名称查找，反之亦然。

globals() 和 locals() 函数各自返回当前的全局和本地字典，因此可以将它们传递给 eval() 或 exec() 来使用。


```python
globals()
```




    {'__name__': '__main__',
     '__doc__': 'Automatically created module for IPython interactive environment',
     '__package__': None,
     '__loader__': None,
     '__spec__': None,
     '__builtin__': <module 'builtins' (built-in)>,
     '__builtins__': <module 'builtins' (built-in)>,
     '_ih': ['', 'help(globals)', 'globals()'],
     '_oh': {},
     '_dh': ['D:\\Jupyter\\xuecn_books\\books\\xue_python_kp\\11_built-in_function'],
     'In': ['', 'help(globals)', 'globals()'],
     'Out': {},
     'get_ipython': <bound method InteractiveShell.get_ipython of <ipykernel.zmqshell.ZMQInteractiveShell object at 0x000001E15E70D748>>,
     'exit': <IPython.core.autocall.ZMQExitAutocall at 0x1e160f63978>,
     'quit': <IPython.core.autocall.ZMQExitAutocall at 0x1e160f63978>,
     '_': '',
     '__': '',
     '___': '',
     '_i': 'help(globals)',
     '_ii': '',
     '_iii': '',
     '_i1': 'help(globals)',
     '_i2': 'globals()'}


