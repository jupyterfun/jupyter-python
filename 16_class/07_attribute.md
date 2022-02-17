## 属性

属性指关联到一个对象的值，可以使用点号表达式通过其名称来引用。

可以使用  dir() 函数查看任意对象的属性。

如果属性是可调用对象（例如类，函数，方法等），引用之后可直接调用，也可先赋值给变量再调用。


```python
# 查看 list 对象的属性
dir(list)
```




    ['__add__',
     '__class__',
     '__contains__',
     '__delattr__',
     '__delitem__',
     '__dir__',
     '__doc__',
     '__eq__',
     '__format__',
     '__ge__',
     '__getattribute__',
     '__getitem__',
     '__gt__',
     '__hash__',
     '__iadd__',
     '__imul__',
     '__init__',
     '__init_subclass__',
     '__iter__',
     '__le__',
     '__len__',
     '__lt__',
     '__mul__',
     '__ne__',
     '__new__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__reversed__',
     '__rmul__',
     '__setattr__',
     '__setitem__',
     '__sizeof__',
     '__str__',
     '__subclasshook__',
     'append',
     'clear',
     'copy',
     'count',
     'extend',
     'index',
     'insert',
     'pop',
     'remove',
     'reverse',
     'sort']




```python
# 通过名称 __add__ 引用属性
list.__add__ 
```




    <slot wrapper '__add__' of 'list' objects>




```python
# 直接调用属性
list.__add__([1,2],[3,4])
```




    [1, 2, 3, 4]




```python
# 赋值给变量再调用
la = list.__add__
la([1,2],[3,4])
```




    [1, 2, 3, 4]



有时也只将具体的值称为属性从而与抽象的值（类，函数，方法等对象的值）区分开来。例如将一个人有身体和四肢的属性和这个人会唱歌跳舞的属性区分开来。


```python
import pandas as pd
pd.Series # pandas 模块的属性 Series 类
```




    pandas.core.series.Series




```python
import math
math.pi # math 模块的属性圆周率
```




    3.141592653589793




```python
class A:
    a = 1
    def f(self):
        print(self)
        
a = A()
A.a, a.a # 类 A 及其实例的数据属性 a
```




    (1, 1)




```python
A.f, a.f # 类 A 及其实例的方法属性 f
```




    (<function __main__.A.f(self)>,
     <bound method A.f of <__main__.A object at 0x000001B569DC0860>>)




```python
# 方法属性的等价调用
# 实例直接调用，第一个参数 self 就是它自身
a.f()
# 类直接调用，则需要传入实例作为参数
A.f(a)
```

    <__main__.A object at 0x000001B569DC0860>
    <__main__.A object at 0x000001B569DC0860>
    

属性名以一个下划线开头的属性应该视为 “私有” 属性，但可以直接访问。

属性名以两个下划线开头，非两个下划线结尾的属性，在模块中视为 “私有” 属性，但可以直接访问；在类中属于私有属性，这种名称在类定义中使用时，会以一种混合形式重写以避免在基类及派生类的 “私有” 属性之间出现名称冲突。类的私有属性并非不可访问（使用重写名称可访问），全靠自觉。


```python
class A:
    _a = 1
    def __f():
        pass
dir(A)
```




    ['_A__f',
     '__class__',
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
     '__weakref__',
     '_a']




```python
A._a
```




    1




```python
A._A__f
```




    <function __main__.A.__f()>


