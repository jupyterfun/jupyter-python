## 变量

Python 中绑定对象的名称即为变量。

人们称呼模块、类、函数和方法对象的名称时，习惯直接指代对象本身，而不是把它们当作变量，例如 random，int，print 等，当将它们绑定到另外的名称时，才称新名称为变量（或化名）。


```python
# 函数名称 f 绑定自定义函数对象
def f(x, func): 
    print(func(x))
    
a = '1231' # 变量 a
b = [int,list,set] # 变量 b
c = f # 名称 f 起别名 c

for i in b: # 变量 b 中的项循环赋值给变量 i
    c(a,i)
```

    1231
    ['1', '2', '3', '1']
    {'3', '1', '2'}
    

如果名称绑定在一个代码块中，则为该代码块的局部变量，除非声明为 nonlocal 或 global。

如果名称绑定在模块层级，则为全局变量。(模块代码块的变量既为局部变量又为全局变量。) 

如果变量在一个代码块中被使用但不是在其中定义，则为自由变量。


```python
# 第一个代码块中全局变量 n
n = 100 
```


```python
# 第二个代码块
# random 模块中的全局变量 randint，
# 在此为局部变量，引用后赋值给全局变量 r
import random
r = random.randint
```


```python
# 第三个代码块中 x 为局部变量
# n 和 r 不在该代码块中定义，在该代码块为自由变量
def f(x):
    print(r(x,n))
    
f(1)
```

    22
    

如果代码块中定义了一个局部变量，则其作用域包含该代码块。如果定义发生于函数代码块中，则其作用域会扩展到该函数所包含的任何代码块，除非有某个被包含代码块引入了对该名称的不同绑定。


```python
m = 0
n = 1 # 全局变量 n
def f():
    n = 2 # 局部变量 n
    print(m,n)
f()
```

    0 2
    

改变变量作用域，详见 [global 语句](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/10_statement/19_global.ipynb) 和 [nonlocal 语句](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/10_statement/20_nonlocal.ipynb)。

类变量和实例变量：
- 在类中定义，仅在类层级修改的变量为类变量，实例也可访问类变量；
- 以 `self.name` 命名的变量为实例变量，类不能访问。 


```python
class A:
    a = 1 # 类变量
    def __init__(self):
        self.a = 100 # 实例变量
        self.b = 2
        
a = A()
A.a, a.a, a.b
```




    (1, 100, 2)




```python
A.b # 类 A 不能访问它的实例的变量 b
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-11-f92f3bcfde9d> in <module>
    ----> 1 A.b # 类 A 不能访问它的实例的变量 b
    

    AttributeError: type object 'A' has no attribute 'b'

