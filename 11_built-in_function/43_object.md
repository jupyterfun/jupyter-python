## object 所有类的基类

内置函数（类）object，Python 官方文档描述如下：


```python
help(object)
```

    Help on class object in module builtins:
    
    class object
     |  The most base type
    
    

当被调用时，它不接受任何参数，并返回一个新的无特性实例，并且不能给定任何实例属性。

object 是所有类的基类。它具有所有 Python 类实例的通用方法。


```python
type(object)
```




    type




```python
object()
```




    <object at 0x1de8bc75170>




```python
dir(object)
```




    ['__class__',
     '__delattr__',
     '__dir__',
     '__doc__',
     '__eq__',
     '__format__',
     '__ge__',
     '__getattribute__',
     '__gt__',
     '__hash__',
     '__init__',
     '__init_subclass__',
     '__le__',
     '__lt__',
     '__ne__',
     '__new__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__setattr__',
     '__sizeof__',
     '__str__',
     '__subclasshook__']


