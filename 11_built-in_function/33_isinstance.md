## isinstance() 是给定类的实例？

内置函数 isinstance()，Python 官方文档描述如下：


```python
help(isinstance)
```

    Help on built-in function isinstance in module builtins:
    
    isinstance(obj, class_or_tuple, /)
        Return whether an object is an instance of a class or of a subclass thereof.
        
        A tuple, as in ``isinstance(x, (A, B, ...))``, may be given as the target to
        check against. This is equivalent to ``isinstance(x, A) or isinstance(x, B)
        or ...`` etc.
    
    

如果对象 obj 是给定类的实例或者是其 (直接、间接或虚拟) 子类的实例则返回 True，不是则返回 False。给定的不是类则引发 TypeError 异常。

给定类可以以元组形式传参，obj 是其中任何一个类型的实例就返回 True。


```python
isinstance(1, int)
```




    True




```python
isinstance('abc', (float, complex))
```




    False




```python
# bool 是 int 的子类型，但不是实例
isinstance(bool, int)
```




    False




```python
# True 是 int 的子类的实例
isinstance(True, int)
```




    True




```python
# bool 的实例只有 True 和 False
isinstance(1, bool)
```




    False




```python
# 所有的对象都是 object 的实例
isinstance(object, object)
```




    True




```python
import random # 模块

class A:pass # 自定义类

isinstance(1, object),\
isinstance(int, object),\
isinstance(list, object),\
isinstance(random, object),\
isinstance(A, object)
```




    (True, True, True, True, True)


