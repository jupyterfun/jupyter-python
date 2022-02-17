## 命名空间

命名空间是存放变量的场所。命名空间有局部、全局和内置的，还有对象中的嵌套命名空间。不同命名空间中的变量没有关系。

命名空间通过防止命名冲突来支持模块化。例如，函数 builtins.open 与 os.open 可通过各自的命名空间来区分。


```python
# 函数的局部命名空间，在函数调用时创建
def f():
    x = '函数 f 命名空间中的变量 x'
    print(x)
```


```python
# 全局命名空间
x = '全局命名空间中的变量 x'
# 调用函数 f，与全局命名空间中的 x 无关
f()
```

    函数 f 命名空间中的变量 x
    


```python
# 模块 random 导入创建它自己的局部命名空间
import random
# 定义一个全局变量 randint
def randint():
    print('全局 randint')
# random 局部命名空间中的 randint 
# 与全局变量 randint 无关
randint()
random.randint(0,3)
```

    全局 randint
    




    1




```python
# 上述定义的变量 f, x, randint，导入的变量 random，
# 都存放在了当前全局命名空间中
f, x, random, randint
```




    (<function __main__.f()>,
     '全局命名空间中的变量 x',
     <module 'random' from 'C:\\ProgramData\\Anaconda3\\lib\\random.py'>,
     <function __main__.randint()>)



内置命名空间是在 Python 解释器启动时创建，存放的变量包括内置函数、异常等。


```python
# 全局命名空间中定义变量 str，
# 将屏蔽内置命名空间中的 str
def str(x):
    return f'x = {x}'
str(123)
```




    'x = 123'




```python
# 但可以在 builtins 中继续调用
import builtins

builtins.str(123)
```




    '123'



递归函数，每次递归调用，都会有一个新的命名空间。


```python
def f(x):
    if x > 0:
        print(f'x={x}调用，x-1={x-1}继续调用')
    if x == 0:
        print(f'x={x},调用结束')
    else:
        # 以 x-1 作为参数调用函数 f
        return f(x-1)
f(3)
```

    x=3调用，x-1=2继续调用
    x=2调用，x-1=1继续调用
    x=1调用，x-1=0继续调用
    x=0,调用结束
    

嵌套的命名空间：


```python
a = '全局变量 a'
class A:
    a = '类变量 a'
    def f(self):
        a = '函数局部变量 a'
        return a

print(a)
print(A.a)
print(A().f())
```

    全局变量 a
    类变量 a
    函数局部变量 a
    
