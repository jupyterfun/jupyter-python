## hasattr() 是对象的属性吗？

内置函数 hasattr()，Python 官方文档描述如下：


```python
help(hasattr)
```

    Help on built-in function hasattr in module builtins:
    
    hasattr(obj, name, /)
        Return whether the object has an attribute with the given name.
        
        This is done by calling getattr(obj, name) and catching AttributeError.
    
    

该函数实参是一个对象和一个字符串。如果字符串是对象的属性之一的名称，则返回 True，否则返回 False。


```python
hasattr('abc', 'join')
```




    True




```python
class A:
    y = 1

hasattr(A, 'y')
```




    True


