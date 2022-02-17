## super 调用委托给父类或兄弟类

内置函数（类）super，Python 官方文档描述如下：


```python
help(super)
```

    Help on class super in module builtins:
    
    class super(object)
     |  super() -> same as super(__class__, <first argument>)
     |  super(type) -> unbound super object
     |  super(type, obj) -> bound super object; requires isinstance(obj, type)
     |  super(type, type2) -> bound super object; requires issubclass(type2, type)
     |  Typical use to call a cooperative superclass method:
     |  class C(B):
     |      def meth(self, arg):
     |          super().meth(arg)
     |  This works for class methods too:
     |  class C(B):
     |      @classmethod
     |      def cmeth(cls, arg):
     |          super().cmeth(arg)
     |  
     |  Methods defined here:
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
     |  __repr__(self, /)
     |      Return repr(self).
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
     |  __self__
     |      the instance invoking super(); may be None
     |  
     |  __self_class__
     |      the type of the instance invoking super(); may be None
     |  
     |  __thisclass__
     |      the class invoking super()
    
    

返回一个代理对象，它会将方法调用委托给类 type 的父类或兄弟类。这对于访问已在类中被重载的继承方法很有用。

- `super()` 和 `super(__class__, <first argument>)` 一样。
- 如果省略第二个参数，则返回的超类对象是未绑定的。
- 如果第二个参数为一个对象，则 isinstance(obj, type) 必须为真值。
- 如果第二个参数为一个类型，则 issubclass(type2, type) 必须为真值（这适用于类方法）。

super 有两个典型用例：
- 在具有单继承的类层级结构中，super 可用来引用父类而不必显式地指定它们的名称，从而令代码更易维护。
- 第二个用例是在动态执行环境中支持协作多重继承。此用例为 Python 所独有。这使得实现 “菱形图” 成为可能，在这时会有多个基类实现相同的方法。好的设计强制要求这种方法在每个情况下具有相同的调用签名（因为调用顺序是在运行时确定的，也因为该顺序要适应类层级结构的更改，还因为该顺序可能包含在运行时之前未知的兄弟类）。

类或方法的 `__mro__` 属性列出了 getattr() 和 super() 所共同使用的方法解析顺序（MRO）。该属性是动态的，可以在任何继承层级结构发生更新的时候被改变。

除了方法查找之外，super() 也可用于属性查找。一个可能的应用场合是在上级或同级类中调用描述器。

请注意 super() 是作为显式加点属性查找的绑定过程的一部分来实现的，例如 `super().__getitem__(name)`。它做到这一点是通过实现自己的 `__getattribute__()` 方法，这样就能以可预测的顺序搜索类，并且支持协作多重继承。

还要注意的是，除了零个参数的形式以外，super() 并不限于在方法内部使用。两个参数的形式明确指定参数并进行相应的引用。零个参数的形式仅适用于类定义内部，因为编译器需要填入必要的细节以正确地检索到被定义的类，还需要让普通方法访问当前实例。

方法调用委托给父类：


```python
type(super)
```




    type




```python
class A:
    def add(self, x):
        y = x + x
        print(y)
            
class B(A):
    def add(self, x):
        super().add(x) # super() 等价于 super(B,self)
        
b = B()
b.add(5)
```

    10
    

初始化委托给父类：


```python
class A:
    def __init__(self):
        self.a = '父类A'
        print ('A')

    def print_msg(self,a):
        print (f'{a}来自A')

class B(A):
    def __init__(self):
        # super(B, self) 可写为 super()
        super(B, self).__init__() 
        print ('B')

    def print_msg(self,b):
        super().print_msg(b)
        print (f'{b}来自B')
        print (self.a)

b = B()
b.print_msg('HelloWorld')
```

    A
    B
    HelloWorld来自A
    HelloWorld来自B
    父类A
    
