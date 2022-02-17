## 属性操作

Python 是动态语言，对象的属性不仅可以查看、访问、调用，还可以动态地增、删、改。

下面定义一个没有自定义属性的类 A 举例：

dir() 函数查看属性，双下划线 `__` 包围的属性是继承自 object 的特殊属性：


```python
# 定义一个类，查看属性
class A:
    pass

dir(A)
```




    ['__class__',
     '__delattr__',
     '__dict__',
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
     '__module__',
     '__ne__',
     '__new__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__setattr__',
     '__sizeof__',
     '__str__',
     '__subclasshook__',
     '__weakref__']




```python
# 访问属性 __class__ 相当于调用 type() 函数
A.__class__, A().__class__
```




    (type, __main__.A)



给类 A 及其实例动态添加属性，属性可以是数据属性和方法。类层级添加的属性，将作为所有实例的属性；实例添加的属性，只有对应的实例能访问。


```python
# 添加数据属性
a1 = A()
a2 = A()
A.a = '类变量'
a1.x = 'a1 的属性'
a2.y = 'a2 的属性'
```


```python
# 类层级添加方法
def f(self):
    print(self.a)

A.f = f
```


```python
# 类 A 调用刚添加的属性
A.f(a1)
A.f(a2)
```

    类变量
    类变量
    


```python
# 实例调用刚添加的属性
a1.f()
a2.f()
```

    类变量
    类变量
    


```python
# 实例 a1 没有 y 属性
# 同理，a2 没有 x 属性
a1.y 
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-44-178a7ac627a0> in <module>
          1 # 实例 a1 没有 y 属性
          2 # 同理，a2 没有 x 属性
    ----> 3 a1.y
    

    AttributeError: 'A' object has no attribute 'y'


实例直接添加一个函数作为属性，将不会隐式地将自身作为第一个参数，而是和正常函数一样使用：


```python
def p(self):
    print(self)

a1.p = p
a1.p('正常传参')
a1.p()
```

    正常传参
    


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-45-4ebdece61250> in <module>
          4 a1.p = p
          5 a1.p('正常传参')
    ----> 6 a1.p()
    

    TypeError: p() missing 1 required positional argument: 'self'


如果要通过实例添加实例方法（第一个参数 self 即是自身的方法），可以通过 types 模块添加。添加的属性，类不可访问，只有对应的实例可访问：


```python
from types import MethodType

# 改变了 a1 的上述 p 属性
a1.p = MethodType(p, a1)
a1.p()
```

    <__main__.A object at 0x000001D40578D730>
    


```python
A.p
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-47-94cb580acfb0> in <module>
    ----> 1 A.p
    

    AttributeError: type object 'A' has no attribute 'p'



```python
a2.p
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-48-29321b2aa581> in <module>
    ----> 1 a2.p
    

    AttributeError: 'A' object has no attribute 'p'


删除属性使用 del 语句：


```python
del a1.p

a1.p()
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-49-9cf9b7e7dc86> in <module>
          1 del a1.p
          2 
    ----> 3 a1.p()
    

    AttributeError: 'A' object has no attribute 'p'

