## callable() 是可调用对象？

内置函数 callable()，Python 官方文档描述如下：


```python
help(callable)
```

    Help on built-in function callable in module builtins:
    
    callable(obj, /)
        Return whether the object is callable (i.e., some kind of function).
        
        Note that classes are callable, as are instances of classes with a
        __call__() method.
    
    

如果 obj 是可调用对象就返回 True，否则返回 False。如果返回 True，调用仍可能失败，但如果返回 False，则调用将肯定不会成功。

函数、方法、类以及实现了 `__call__()` 方法的类的实例是可调用的。


```python
callable(1)
```




    False




```python
callable(int)
```




    True




```python
class Myint(int):
    def __call__(self):
        pass
num = Myint(1)
num
```




    1




```python
callable(num)
```




    True




```python
callable(lambda: 1)
```




    True


