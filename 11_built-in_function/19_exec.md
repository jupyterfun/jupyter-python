## exec() 解析字符串或代码并求值

内置函数 exec()，Python 官方文档描述如下：


```python
help(exec)
```

    Help on built-in function exec in module builtins:
    
    exec(source, globals=None, locals=None, /)
        Execute the given source in the context of globals and locals.
        
        The source may be a string representing one or more Python statements
        or a code object as returned by compile().
        The globals must be a dictionary and locals can be any mapping,
        defaulting to the current globals and locals.
        If only globals is given, locals defaults to it.
    
    

这个函数支持动态执行 Python 代码。source 必须是字符串或者代码对象。

如果是字符串，那么该字符串将被解析为一系列 Python 语句并执行（除非发生语法错误）。

如果是代码对象，它将被直接执行。

该函数返回值为 None。


```python
print(exec('{1 + 1}'))
```

    None
    


```python
s = 'for i in range(3):print(i)'
code = compile(s,'','exec')
exec(code)
```

    0
    1
    2
    

参数 globals 和 locals 作为 source 的全局和局部命名空间。如果省略 locals 字典则其默认值为 globals 字典。如果两个字典同时省略，则表达式执行时会使用 eval() 被调用的环境中的全局和局部名称。

如果 globals 字典存在且不包含以 `__builtins__` 为键的值，则将为该键插入对内建 builtins 模块字典的引用。因此，在将执行的代码传递给 exec() 之前，可以通过将自己的 `__builtins__` 字典插入到 globals 中来控制可以使用哪些内置代码。

globals 实参必须是一个字典。locals 可以是任何映射对象。


```python
x = 1
def f():
    x = 2
    code = "for i in range(x):print(i)"
    exec(code,{'x':3},{'x':4})
f()
```

    0
    1
    2
    3
    


```python
x = 1
def f():
    x = 2
    code = "for i in range(x):print(i)"
    exec(code,{'x':3})
f()
```

    0
    1
    2
    


```python
x = 1
def f():
    x = 2
    code = "for i in range(x):print(i)"
    exec(code)
f()
```

    0
    1
    
