## classmethod 封装函数为类方法

内置函数（类）classmethod，Python 官方文档描述如下：


```python
help(classmethod)
```

    Help on class classmethod in module builtins:
    
    class classmethod(object)
     |  classmethod(function) -> method
     |  
     |  Convert a function to be a class method.
     |  
     |  A class method receives the class as implicit first argument,
     |  just like an instance method receives the instance.
     |  To declare a class method, use this idiom:
     |  
     |    class C:
     |        @classmethod
     |        def f(cls, arg1, arg2, ...):
     |            ...
     |  
     |  It can be called either on the class (e.g. C.f()) or on an instance
     |  (e.g. C().f()).  The instance is ignored except for its class.
     |  If a class method is called for a derived class, the derived class
     |  object is passed as the implied first argument.
     |  
     |  Class methods are different than C++ or Java static methods.
     |  If you want those, see the staticmethod builtin.
     |  
     |  Methods defined here:
     |  
     |  __get__(self, instance, owner, /)
     |      Return an attribute of instance, which is of type owner.
     |  
     |  __init__(self, /, *args, **kwargs)
     |      Initialize self.  See help(type(self)) for accurate signature.
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
     |  __dict__
     |  
     |  __func__
     |  
     |  __isabstractmethod__
    
    

把一个函数封装成类方法。一个类方法把类自己作为第一个实参，就像一个实例方法把实例自己作为第一个实参。

可将函数作为参数来声明类方法，但请用习惯的装饰器形式（@classmethod）来声明类方法。


```python
type(classmethod)
```




    type




```python
class A:
    print_itself = classmethod(print)

A.print_itself()
```

    <class '__main__.A'>
    


```python
class A:
    @classmethod
    def print_itself(cls):
        print(cls)

A.print_itself()
```

    <class '__main__.A'>
    
