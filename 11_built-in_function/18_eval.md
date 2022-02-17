## eval() 解析字符串或代码并求值

内置函数 eval()，Python 官方文档描述如下：


```python
help(eval)
```

    Help on built-in function eval in module builtins:
    
    eval(source, globals=None, locals=None, /)
        Evaluate the given source in the context of globals and locals.
        
        The source may be a string representing a Python expression
        or a code object as returned by compile().
        The globals must be a dictionary and locals can be any mapping,
        defaulting to the current globals and locals.
        If only globals is given, locals defaults to it.
    
    

source 参数接受字符串（会作为一个 Python 表达式）或代码对象（可通过 compile() 创建），然后解析并求值，返回求值结果。


```python
eval('{1 + 1}')
```




    {2}




```python
s = 'for i in range(3):print(i)'
code = compile(s,'','exec')
eval(code)
```

    0
    1
    2
    


```python
eval("__import__('math').sqrt(3**2+4**2)")
```




    5.0



参数 globals 和 locals 作为 source 的全局和局部命名空间。如果省略 locals 字典则其默认值为 globals 字典。如果两个字典同时省略，则表达式执行时会使用 eval() 被调用的环境中的全局和局部名称。

如果 globals 字典存在且不包含以 `__builtins__` 为键的值，则会在解析 source 之前插入以此为键的对内置模块 builtins 的引用。这意味着 source 通常具有对标准 builtins 模块的完全访问权限且受限的环境会被传播。

globals 实参必须是一个字典。locals 可以是任何映射对象。


```python
x = 3
def f():
    y = 4
    code = "__import__('math').sqrt(x**2+y**2)"
    z = eval(code,{'x':5},{'y':12})
    print(f'x={x}, y={y}, z={z}')
f()
```

    x=3, y=4, z=13.0
    


```python
x = 3
def f():
    y = 4
    code = "__import__('math').sqrt(x**2+y**2)"
    z = eval(code,{'x':5,'y':12})
    print(f'x={x}, y={y}, z={z}')
f()
```

    x=3, y=4, z=13.0
    


```python
x = 3
def f():
    y = 4
    code = "__import__('math').sqrt(x**2+y**2)"
    z = eval(code)
    print(f'x={x}, y={y}, z={z}')
f()
```

    x=3, y=4, z=5.0
    
