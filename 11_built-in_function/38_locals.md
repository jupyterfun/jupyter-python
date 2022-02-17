## locals() 返回局部变量的字典

内置函数 locals()，Python 官方文档描述如下：


```python
help(locals)
```

    Help on built-in function locals in module builtins:
    
    locals()
        Return a dictionary containing the current scope's local variables.
        
        NOTE: Whether or not updates to this dictionary will affect name lookups in
        the local scope and vice-versa is *implementation dependent* and not
        covered by any backwards compatibility guarantees.
    
    

返回包含当前作用域的局部变量的字典。在模块层级上，locals() 和 globals() 是同一个字典。

globals() 和 locals() 函数各自返回当前的全局和本地字典，因此可以将它们传递给 eval() 或 exec() 来使用。


```python
locals()
```




    {'__name__': '__main__',
     '__doc__': 'Automatically created module for IPython interactive environment',
     '__package__': None,
     '__loader__': None,
     '__spec__': None,
     '__builtin__': <module 'builtins' (built-in)>,
     '__builtins__': <module 'builtins' (built-in)>,
     '_ih': ['', 'help(locals)', 'locals()'],
     '_oh': {},
     '_dh': ['D:\\Jupyter\\xuecn_books\\books\\xue_python_kp\\11_built-in_function'],
     'In': ['', 'help(locals)', 'locals()'],
     'Out': {},
     'get_ipython': <bound method InteractiveShell.get_ipython of <ipykernel.zmqshell.ZMQInteractiveShell object at 0x0000023E24AE89B0>>,
     'exit': <IPython.core.autocall.ZMQExitAutocall at 0x23e27368898>,
     'quit': <IPython.core.autocall.ZMQExitAutocall at 0x23e27368898>,
     '_': '',
     '__': '',
     '___': '',
     '_i': 'help(locals)',
     '_ii': '',
     '_iii': '',
     '_i1': 'help(locals)',
     '_i2': 'locals()'}




```python
def f():
    a = 1
    print(locals())
f()
```

    {'a': 1}
    
