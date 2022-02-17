## delattr() 删除对象属性

内置函数 delattr()，Python 官方文档描述如下：


```python
help(delattr)
```

    Help on built-in function delattr in module builtins:
    
    delattr(obj, name, /)
        Deletes the named attribute from the given object.
        
        delattr(x, 'y') is equivalent to ``del x.y''
    
    

实参是一个对象和一个字符串。该字符串必须是对象的某个属性。如果对象允许，该函数将删除指定的属性。`delattr(x, 'y')` 等价于 `del x.y`。


```python
class A:
    y = 0

x = A
x.y
```




    0




```python
delattr(x,'y')
```


```python
x.y
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-12-3552434a3e61> in <module>
    ----> 1 x.y
    

    AttributeError: type object 'A' has no attribute 'y'

