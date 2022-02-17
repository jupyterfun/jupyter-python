## vars() 返回对象的变量字典

内置函数 vars()，Python 官方文档描述如下：


```python
help(vars)
```

    Help on built-in function vars in module builtins:
    
    vars(...)
        vars([object]) -> dictionary
        
        Without arguments, equivalent to locals().
        With an argument, equivalent to object.__dict__.
    
    

返回模块、类、实例或任何其它具有 `__dict__` 属性的对象的 `__dict__` 属性。

模块和实例这样的对象具有可更新的 `__dict__` 属性；但是，其它对象的 `__dict__` 属性可能会设为限制写入（例如，类会使用`types.MappingProxyType` 来防止直接更新字典）。

不带参数时，vars() 的行为类似 locals()。请注意，locals 字典仅对于读取起作用，因为对 locals 字典的更新会被忽略。

如果指定了一个对象但它没有 `__dict__` 属性则会引发TypeError 异常。


```python
vars()
```




    {'__name__': '__main__',
     '__doc__': 'Automatically created module for IPython interactive environment',
     '__package__': None,
     '__loader__': None,
     '__spec__': None,
     '__builtin__': <module 'builtins' (built-in)>,
     '__builtins__': <module 'builtins' (built-in)>,
     '_ih': ['', "get_ipython().run_line_magic('pinfo', 'vars')", 'vars()'],
     '_oh': {},
     '_dh': ['E:\\xue\\脚本\\kp_book\\11_built-in_function'],
     'In': ['', "get_ipython().run_line_magic('pinfo', 'vars')", 'vars()'],
     'Out': {},
     'get_ipython': <bound method InteractiveShell.get_ipython of <ipykernel.zmqshell.ZMQInteractiveShell object at 0x00000189A6512310>>,
     'exit': <IPython.core.autocall.ZMQExitAutocall at 0x189a65b32e0>,
     'quit': <IPython.core.autocall.ZMQExitAutocall at 0x189a65b32e0>,
     '_': '',
     '__': '',
     '___': '',
     '_i': 'vars?',
     '_ii': '',
     '_iii': '',
     '_i1': 'vars?',
     '_i2': 'vars()'}




```python
def f():pass
vars(f)
```




    {}




```python
f.__dict__['a'] = 1
f.a
```




    1




```python
vars(1)
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-9-3391faf83557> in <module>
    ----> 1 vars(1)
    

    TypeError: vars() argument must have __dict__ attribute

