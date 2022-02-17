## getattr() 获取对象的属性

内置函数 getattr()，Python 官方文档描述如下：


```python
help(getattr)
```

    Help on built-in function getattr in module builtins:
    
    getattr(...)
        getattr(object, name[, default]) -> value
        
        Get a named attribute from an object; getattr(x, 'y') is equivalent to x.y.
        When a default argument is given, it is returned when the attribute doesn't
        exist; without it, an exception is raised in that case.
    
    

返回对象给定的属性名指向的值。name 必须是字符串。如果该字符串是对象的属性名称之一，则返回该属性的值。例如，`getattr(x, 'y')` 等同于 `x.y`。如果指定的属性不存在，且提供了 default 值，则返回它，否则触发 AttributeError。


```python
getattr(1,'imag')
```




    0




```python
getattr(1,'bool',True)
```




    True




```python
getattr(1,'bool')
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-6-524bb2b35e58> in <module>
    ----> 1 getattr(1,'bool')
    

    AttributeError: 'int' object has no attribute 'bool'



```python
class A:
    y = 1
x = A()
x.y
```




    1




```python
getattr(x,'y')
```




    1


