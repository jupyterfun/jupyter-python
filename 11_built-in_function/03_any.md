## any() 有一个元素布尔值为真？

内置函数 any()，Python 官方文档描述如下：


```python
help(any)
```

    Help on built-in function any in module builtins:
    
    any(iterable, /)
        Return True if bool(x) is True for any x in the iterable.
        
        If the iterable is empty, return False.
    
    

如果可迭代对象（iterable）的任一元素为真值则返回 True。如果可迭代对象为空，返回 False。


```python
any([0,1])
```




    True




```python
any((None, [], range(1,1)))
```




    False


