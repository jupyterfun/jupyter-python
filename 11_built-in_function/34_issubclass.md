## issubclass() 是给定类的子类吗？

内置函数 issubclass()，Python 官方文档描述如下：


```python
help(issubclass)
```

    Help on built-in function issubclass in module builtins:
    
    issubclass(cls, class_or_tuple, /)
        Return whether 'cls' is a derived from another class or is the same class.
        
        A tuple, as in ``issubclass(x, (A, B, ...))``, may be given as the target to
        check against. This is equivalent to ``issubclass(x, A) or issubclass(x, B)
        or ...`` etc.
    
    

如果类 cls 是给定类的 (直接、间接或虚拟) 子类则返回 True，不是则返回 False。给定的不是类则引发 TypeError 异常。

给定类可以以元组形式传参，cls 是其中任何一个类的子类就返回 True。


```python
issubclass(1, int) # 1 不是类
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-2-257e7a8dbb04> in <module>
    ----> 1 issubclass(1, int)
    

    TypeError: issubclass() arg 1 must be a class



```python
issubclass(bool, int)
```




    True




```python
issubclass(bool, (set, str, list))
```




    False




```python
# 所有的类都是 object 的子类
class A:pass
issubclass(A, object),\
issubclass(str, object),\
issubclass(object, object)
```




    (True, True, True)


