## 类继承

所有的类都继承自 object。被继承的类称为基类（或父类，超类），继承者称为子类。
	
对于多数应用来说，在最简单的情况下，你可以认为搜索从父类所继承属性的操作是**深度优先、从左至右**的，当层次结构中存在重叠时不会在同一个类中搜索两次。
	


```python
class A():
    def show(self):
        print('A')

class B(A):
    pass

class C():
    pass

class D():
    def show(self):
        print('D')

class E(C, B, D):  # C -> B -> A -> D
    pass

e = E()
e.show()
```

    A
    

真实情况比这个更复杂一些；方法解析顺序会动态改变以支持对 super() 的协同调用。这种方式在某些其他多重继承型语言中被称为 后续方法调用，它比单继承型语言中的 super 调用更强大。

动态改变顺序是有必要的，因为所有多重继承的情况都会显示出一个或更多的菱形关联（即至少有一个父类可通过多条路径被最底层类所访问）。例如，所有类都是继承自 object，因此任何多重继承的情况都提供了一条以上的路径可以通向 object。为了确保基类不会被访问一次以上，动态算法会用一种特殊方式将搜索顺序线性化，保留每个类所指定的从左至右的顺序，只调用每个父类一次，并且保持单调（即一个类可以被子类化而不影响其父类的优先顺序）。

总而言之，这些特性使得设计具有多重继承的可靠且可扩展的类成为可能。

一个基类如果有 `__init__()` 方法，则其所派生的类如果也有 `__init__()` 方法，就必须显式地调用它以确保实例基类部分的正确初始化：


```python
class A:
    def __init__(self):
        self.a = 'A'
    
    def f(self):
        print(self.a)
        
class B(A):
    def __init__(self):
        self.b = 'B'

b = B()
b.f() # 基类未初始化，属性 a 不可调用
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-5-cda60db4451f> in <module>
         11 
         12 b = B()
    ---> 13 b.f()
    

    <ipython-input-5-cda60db4451f> in f(self)
          4 
          5     def f(self):
    ----> 6         print(self.a)
          7 
          8 class B(A):
    

    AttributeError: 'B' object has no attribute 'a'



```python
A.__init__(b) # 将实例 b 传给 A 初始化
b.f()
```

    A
    


```python
# 或者直接用 super()
class A:
    def __init__(self):
        self.a = 'A'
    
    def f(self):
        print(self.a)
        
class B(A):
    def __init__(self):
        super().__init__()
        self.b = 'B'

b = B()
b.f()
```

    A
    
