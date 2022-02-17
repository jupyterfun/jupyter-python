## repr() 返回对象的可打印字符串

内置函数 repr()，Python 官方文档描述如下：


```python
help(repr)
```

    Help on built-in function repr in module builtins:
    
    repr(obj, /)
        Return the canonical string representation of the object.
        
        For many object types, including most builtins, eval(repr(obj)) == obj.
    
    

返回包含一个对象的可打印表示形式的字符串。

对于许多类型来说，该函数会尝试返回的字符串将会与该对象被传递给 eval() 时所生成的对象具有相同的值，在其他情况下表示形式会是一个括在尖括号中的字符串，其中包含对象类型的名称与通常包括对象名称和地址的附加信息。


```python
repr(1+1)
```




    '2'




```python
repr(int)
```




    "<class 'int'>"




```python
str('python\n')
```




    'python\n'




```python
repr('python\n')
```




    "'python\\n'"


