## type 判断类型或创建类

内置函数（类）type，Python 官方文档描述如下：


```python
help(type)
```

    Help on class type in module builtins:
    
    class type(object)
     |  type(object_or_name, bases, dict)
     |  type(object) -> the object's type
     |  type(name, bases, dict) -> a new type
     |  
     |  Methods defined here:
     |  
     |  __call__(self, /, *args, **kwargs)
     |      Call self as a function.
     |  
     |  __delattr__(self, name, /)
     |      Implement delattr(self, name).
     |  
     |  __dir__(self, /)
     |      Specialized __dir__ implementation for types.
     |  
     |  __getattribute__(self, name, /)
     |      Return getattr(self, name).
     |  
     |  __init__(self, /, *args, **kwargs)
     |      Initialize self.  See help(type(self)) for accurate signature.
     |  
     |  __instancecheck__(self, instance, /)
     |      Check if an object is an instance.
     |  
     |  __repr__(self, /)
     |      Return repr(self).
     |  
     |  __setattr__(self, name, value, /)
     |      Implement setattr(self, name, value).
     |  
     |  __sizeof__(self, /)
     |      Return memory consumption of the type object.
     |  
     |  __subclasscheck__(self, subclass, /)
     |      Check if a class is a subclass.
     |  
     |  __subclasses__(self, /)
     |      Return a list of immediate subclasses.
     |  
     |  mro(self, /)
     |      Return a type's method resolution order.
     |  
     |  ----------------------------------------------------------------------
     |  Class methods defined here:
     |  
     |  __prepare__(...)
     |      __prepare__() -> dict
     |      used to create the namespace for the class statement
     |  
     |  ----------------------------------------------------------------------
     |  Static methods defined here:
     |  
     |  __new__(*args, **kwargs)
     |      Create and return a new object.  See help(type) for accurate signature.
     |  
     |  ----------------------------------------------------------------------
     |  Data descriptors defined here:
     |  
     |  __abstractmethods__
     |  
     |  __dict__
     |  
     |  __text_signature__
     |  
     |  ----------------------------------------------------------------------
     |  Data and other attributes defined here:
     |  
     |  __base__ = <class 'object'>
     |      The most base type
     |  
     |  __bases__ = (<class 'object'>,)
     |  
     |  __basicsize__ = 864
     |  
     |  __dictoffset__ = 264
     |  
     |  __flags__ = -2146675712
     |  
     |  __itemsize__ = 40
     |  
     |  __mro__ = (<class 'type'>, <class 'object'>)
     |  
     |  __weakrefoffset__ = 368
    
    

传入一个参数时，返回对象的类型。推荐使用 isinstance() 内置函数来检测对象的类型，因为它会考虑子类的情况。

传入三个参数时，返回一个新的 type 对象。这在本质上是 class 语句的一种动态形式。name 参数是字符串即类名并且会成为 `__name__` 属性；bases 元组列出基类并且会成为 `__bases__` 属性；而 dict 字典为包含类主体定义的命名空间并且会被复制到一个标准字典成为 `__dict__` 属性。


```python
type(type)
```




    type




```python
type(int), type(object)
```




    (type, type)




```python
isinstance(int, object)
```




    True




```python
class A:
    a = 1
A.__name__, A.__bases__, A.__dict__
```




    ('A',
     (object,),
     mappingproxy({'__module__': '__main__',
                   'a': 1,
                   '__dict__': <attribute '__dict__' of 'A' objects>,
                   '__weakref__': <attribute '__weakref__' of 'A' objects>,
                   '__doc__': None}))




```python
A = type('A', (object,), dict(a=1))
A.__name__, A.__bases__, A.__dict__
```




    ('A',
     (object,),
     mappingproxy({'a': 1,
                   '__module__': '__main__',
                   '__dict__': <attribute '__dict__' of 'A' objects>,
                   '__weakref__': <attribute '__weakref__' of 'A' objects>,
                   '__doc__': None}))


