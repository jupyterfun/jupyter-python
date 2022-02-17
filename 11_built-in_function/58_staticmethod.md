## staticmethod 封装函数为静态方法

内置函数（类）staticmethod，Python 官方文档描述如下：


```python
help(staticmethod)
```

    Help on class staticmethod in module builtins:
    
    class staticmethod(object)
     |  staticmethod(function) -> method
     |  
     |  Convert a function to be a static method.
     |  
     |  A static method does not receive an implicit first argument.
     |  To declare a static method, use this idiom:
     |  
     |       class C:
     |           @staticmethod
     |           def f(arg1, arg2, ...):
     |               ...
     |  
     |  It can be called either on the class (e.g. C.f()) or on an instance
     |  (e.g. C().f()).  The instance is ignored except for its class.
     |  
     |  Static methods in Python are similar to those found in Java or C++.
     |  For a more advanced concept, see the classmethod builtin.
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
    
    

将函数转换为静态方法。

静态方法不会接收隐式的第一个参数。可以传递一个函数作为参数定义为静态方法，也可以使用装饰器的形式将一个自定义函数定义为静态方法。


```python
type(staticmethod)
```




    type




```python
class A:
    in_print = staticmethod(print)
a = A()
a.in_print('静态方法')
```

    静态方法
    


```python
class A:
    @staticmethod
    def in_print(value):
        print(value)
a = A()
a.in_print('静态方法')
```

    静态方法
    
