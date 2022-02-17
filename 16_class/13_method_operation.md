## 方法操作

一个从父类继承过来的方法，如果不满足子类的需求，可以进行重写，重写的方法将屏蔽父类的方法，但可以显示地调用，或使用 super() 委托给父类调用，实现父类、子类的方法都可调用。


```python
class A:
    def f(self,x):
        y = x + x
        print(y)
class B(A):
    def f(self,x):
        y = (x + x)**2 
        print(y)

b = B()
b.f(2)
```

    16
    


```python
# 显示地调用
A.f(b, 2)
```

    4
    


```python
class A:
    def f(self,x):
        y = x + x
        print(y)
class B(A):
    def f(self,x):
        super().f(x)
        y = (x + x)**2 
        print(y)

b = B()
b.f(2)
```

    4
    16
    

还可使用装饰器修改方法，或添加丰富功能等。


```python
# 将方法定义为静态方法
class C:
    @staticmethod
    def f(value):
        print(value)
c = C()
c.f('必须传参调用')
```

    必须传参调用
    


```python
# 将私有属性定义为只读，
# 直接用不带下划线的名称访问
class C:
    def __init__(self):
        self.__name = '私有属性'
    @property
    def name(self):
        return self.__name
c = C()
c.name
```




    '私有属性'




```python
# 尝试修改不被允许
c.name = 0
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-11-c0f354f546f5> in <module>
          1 # 尝试修改不被允许
    ----> 2 c.name = 0
    

    AttributeError: can't set attribute


用特殊方法定制类：


```python
class D:
    pass

d = D()
bool(d)
```




    True




```python
# 上述类的实例逻辑值检查为 True
# 定义为 False
class D:
    def __bool__(self):
        return False
d = D()
bool(d)
```




    False




```python
# 让数字字符串也可以相减
class Mystr(str):
    def __sub__(self, other):
        return str(float(self) - float(other))
m = Mystr('123')
n = Mystr('3.14')
m, n, m - n
```




    ('123', '3.14', '119.86')


