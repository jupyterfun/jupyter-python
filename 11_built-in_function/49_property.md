## property 返回 property 属性

内置函数（类）property，Python 官方文档描述如下：


```python
help(property)
```

    Help on class property in module builtins:
    
    class property(object)
     |  property(fget=None, fset=None, fdel=None, doc=None)
     |  
     |  Property attribute.
     |  
     |    fget
     |      function to be used for getting an attribute value
     |    fset
     |      function to be used for setting an attribute value
     |    fdel
     |      function to be used for del'ing an attribute
     |    doc
     |      docstring
     |  
     |  Typical use is to define a managed attribute x:
     |  
     |  class C(object):
     |      def getx(self): return self._x
     |      def setx(self, value): self._x = value
     |      def delx(self): del self._x
     |      x = property(getx, setx, delx, "I'm the 'x' property.")
     |  
     |  Decorators make defining new properties or modifying existing ones easy:
     |  
     |  class C(object):
     |      @property
     |      def x(self):
     |          "I am the 'x' property."
     |          return self._x
     |      @x.setter
     |      def x(self, value):
     |          self._x = value
     |      @x.deleter
     |      def x(self):
     |          del self._x
     |  
     |  Methods defined here:
     |  
     |  __delete__(self, instance, /)
     |      Delete an attribute of instance.
     |  
     |  __get__(self, instance, owner, /)
     |      Return an attribute of instance, which is of type owner.
     |  
     |  __getattribute__(self, name, /)
     |      Return getattr(self, name).
     |  
     |  __init__(self, /, *args, **kwargs)
     |      Initialize self.  See help(type(self)) for accurate signature.
     |  
     |  __set__(self, instance, value, /)
     |      Set an attribute of instance to value.
     |  
     |  deleter(...)
     |      Descriptor to change the deleter on a property.
     |  
     |  getter(...)
     |      Descriptor to change the getter on a property.
     |  
     |  setter(...)
     |      Descriptor to change the setter on a property.
     |  
     |  ----------------------------------------------------------------------
     |  Static methods defined here:
     |  
     |  __new__(*args, **kwargs) from builtins.type
     |      Create and return a new object.  See help(type) for accurate signature.
     |  
     |  ----------------------------------------------------------------------
     |  Data descriptors defined here:
     |  
     |  __isabstractmethod__
     |  
     |  fdel
     |  
     |  fget
     |  
     |  fset
    
    

返回 property 属性。

fget 是获取属性值的函数。fset 是用于设置属性值的函数。fdel 是用于删除属性值的函数，doc 为属性对象创建文档字符串。


```python
type(property)
```




    type




```python
dir(property)
```




    ['__class__',
     '__delattr__',
     '__delete__',
     '__dir__',
     '__doc__',
     '__eq__',
     '__format__',
     '__ge__',
     '__get__',
     '__getattribute__',
     '__gt__',
     '__hash__',
     '__init__',
     '__init_subclass__',
     '__isabstractmethod__',
     '__le__',
     '__lt__',
     '__ne__',
     '__new__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__set__',
     '__setattr__',
     '__sizeof__',
     '__str__',
     '__subclasshook__',
     'deleter',
     'fdel',
     'fget',
     'fset',
     'getter',
     'setter']



一个典型的用法是定义一个托管属性 x:


```python
# 列一
class C:
    def __init__(self,value):
        self._x = value
    
    def getx(self): 
        return self._x
    
    def setx(self, value): 
        self._x = value
        
    def delx(self): 
        del self._x
        
    x = property(getx, setx, delx, "I'm the 'x' property.")
```

如果 c 是 C 的实例，`c.x` 将调用 getter，`c.x = value` 将调用 setter，`del c.x` 将调用 deleter。

如果给出，doc 将成为该 property 属性的文档字符串。否则该 property 将拷贝 fget 的文档字符串（如果存在）。


```python
c = C(1)
c.x
```




    1




```python
c.x = 2
c.x
```




    2




```python
del c.x
c.x
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-16-d32ce31f0255> in <module>
          1 del c.x
    ----> 2 c.x
    

    <ipython-input-10-eaaa1d84111b> in getx(self)
          4 
          5     def getx(self):
    ----> 6         return self._x
          7 
          8     def setx(self, value):
    

    AttributeError: 'C' object has no attribute '_x'


这令使用 property() 作为装饰器来创建只读的特征属性可以很容易地实现:


```python
class Parrot:
    def __init__(self):
        self._voltage = 100000
    @property
    def voltage(self):
        """Get the current voltage."""
        return self._voltage
```

以上 @property 装饰器会将 voltage() 方法转化为一个具有相同名称的只读属性的 getter，并将 voltage 的文档字符串设置为 ‘Get the current voltage.’


```python
p = Parrot()
p.voltage
```




    100000




```python
p.voltage = 100
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-20-50ba7917c8b5> in <module>
    ----> 1 p.voltage = 100
    

    AttributeError: can't set attribute


特征属性对象具有 getter, setter 以及 deleter 方法，它们可用作装饰器来创建该特征属性的副本，并将相应的访问函数设为所装饰的函数。


```python
class C:
    def __init__(self,value):
        self._x = value
        
    @property
    def x(self):
        """I'm the 'x' property."""
        return self._x
    
    @x.setter
    def x(self, value):
        self._x = value
        
    @x.deleter
    def x(self):
        del self._x
```

上述代码与 例一 完全等价。注意一定要给附加函数与原始的特征属性相同的名称。


```python
c = C(1)
c.x
```




    1




```python
c.x = 2
c.x
```




    2




```python
del c.x
c.x
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-7-d32ce31f0255> in <module>
          1 del c.x
    ----> 2 c.x
    

    <ipython-input-4-356a299284e7> in x(self)
          6     def x(self):
          7         """I'm the 'x' property."""
    ----> 8         return self._x
          9 
         10     @x.setter
    

    AttributeError: 'C' object has no attribute '_x'

