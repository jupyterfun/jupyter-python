## global 语句

global 语句作用于整个当前代码块，它后面所列出的标识符将被解读为全局变量。

在 global 语句中列出的名称不得在同一代码块内该 global 语句之前的位置中使用。

当前的实现虽然并未强制要求，但在 global 语句中列出的名称不得被定义为正式形参，不也得出现于 for 循环的控制目标、class 定义、函数定义、import 语句 或 变量标注之中。

举例如下：


```python
def f():
    a = 0
    
f() # 调用函数，对 a 赋值
a # a 是局部变量，不可访问
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-5-251a24e05273> in <module>
          3 
          4 f() # 调用函数，对 a 赋值
    ----> 5 a # a 是局部变量，不可访问
    

    NameError: name 'a' is not defined



```python
def f():
    global a # 将 a 声明为全局变量
    a = 0
f() # 调用函数，对 a 赋值
print(a) # a 已经是全局变量
del a
```

    0
    


```python
def f():
    a = 1 # 同一代码块中，不可在 global 前使用
    global a # 将 a 声明为全局变量
    a = 0
```


      File "<ipython-input-9-51bc7826eb42>", line 3
        global a # 将 a 声明为全局变量
        ^
    SyntaxError: name 'a' is assigned to before global declaration
    



```python
a = 1 # 与 global 不在一个代码块
def f():
    global a, b # 将 a, b 声明为全局变量
    a = 0 # a 被重新赋值
    b = 1
f() # 调用函数，对 b 赋值，对 a 重新赋值
print(a,b)
del a,b
```

    0 1
    
