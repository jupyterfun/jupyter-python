## 函数形参

形参是函数定义中指定的参数名称。指定某个参数的形式，决定了该形参在函数调用时，可以接受实参的方式。关于实参详见 [函数调用](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/12_function/07_function_call.ipynb)。

因而形参分为五种：

- 位置或关键字：指定一个可以作为 位置参数 传入也可以作为 关键字参数 传入的实参。这是默认的形参类型，但有默认值的形参必须置于无默认值的形参之后。


```python
def f(a,b=None):
    print(f'a={a},b={b}')
# 位置实参传入
f(1,2)
# 关键字实参传入
f(b=2,a=1)
```

    a=1,b=2
    a=1,b=2
    

- 仅限位置：指定一个只能通过位置传入的参数。仅限位置形参通过在函数定义的形参之后包含一个 `/` 字符来定义。`/` 之前的参数为仅限位置形参，之后的形参为默认形参类型。有默认值的形参也必须置于无默认值的形参之后。


```python
def f(a,b=None,/,c=None): # 因为 b 有默认值，c 必须要有默认值
    print(f'a={a},b={b},c={c}')
# 按位置传参调用
f(1,2,c=3)
# 关键字传参则不允许
f(a=1,b=2)
```

    a=1,b=2,c=3
    


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-6-52b3afdaad4c> in <module>
          4 f(1,2,c=3)
          5 # 关键字传参则不允许
    ----> 6 f(a=1,b=2)
    

    TypeError: f() got some positional-only arguments passed as keyword arguments: 'a, b'


- 仅限关键字：指定一个只能通过关键字传入的参数。仅限关键字形参可通过在函数定义的形参中包含单个 可变位置形参 或者在形参之前放一个 `*` 来定义。可变位置形参 或 `*` 之后的参数为仅限关键字形参。


```python
def f(*a,b=None,c=None): # b 和 c 必须有默认值
    print(f'a={a},b={b},c={c}')
# 位置传参将被解读为可变位置参数
f(1,2,3)
# 关键字传参
f(1,b=2,c=3)
```

    a=(1, 2, 3),b=None,c=None
    a=(1,),b=2,c=3
    


```python
def f(*,a,b=None,c):
    print(f'a={a},b={b},c={c}')
# 关键字传参
f(b=2,a=1,c=3)
# 位置传参不允许
f(1,2,3)
```

    a=1,b=2,c=3
    


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-1-9d584fa28622> in <module>
          4 f(b=2,a=1,c=3)
          5 # 位置传参不允许
    ----> 6 f(1,2,3)
    

    TypeError: f() takes 0 positional arguments but 3 were given


- 可变位置：指定一个可以接受任意数量的位置参数传入的参数。这种形参可通过在形参名称前加缀 `*` 来定义，并将接受到的参数封装成一个元组。该参数如果接受到了实参，它前面的参数必须为仅限位置参数。


```python
def f(a,b=None,*c):
    print(f'a={a},b={b},c={c}')
# c 没有接受参数
f(1); f(b=2,a=1)
# c 接受到了参数
f(1,2,3,4,5)
```

    a=1,b=None,c=()
    a=1,b=2,c=()
    a=1,b=2,c=(3, 4, 5)
    

- 可变关键字：指定一个可以接受任意数量的关键字参数的参数。这种形参可通过在形参名称前加缀 `**` 来定义，并将接受到的参数封装成一个字典。


```python
def f(a,b=None,**c):
    print(f'a={a},b={b},c={c}')

f(1,2,c=3,d=4)
f(d=4,b=2,a=1,c=3)
```

    a=1,b=2,c={'c': 3, 'd': 4}
    a=1,b=2,c={'d': 4, 'c': 3}
    

带默认值的参数，可变位置参数和可变关键字参数，调用函数时可以不传参。


```python
def f(a=1,*b,c=3,**d):
    print(f'a={a},b={b},c={c},d={d}')
f()
```

    a=1,b=(),c=3,d={}
    

默认值只会执行一次，这条规则很重要。如果参数有默认值且为可变对象，则需要做必要的限制：


```python
def f(a=[]):
    print(id(a))
    a.append(1)
    print(a)
f() # 多次调用会引用参数指向的同一个对象
f()
```

    2399568560064
    [1]
    2399568560064
    [1, 1]
    


```python
# 可以拷贝一个副本
def f(a=[]):
    b = a.copy()
    b.append(1)
    print(b)
f()
f()
```

    [1]
    [1]
    


```python
# 或者修改参数
def f(a=None):
    if a == None:
        a = []
        a.append(1)
    else:
        a.append(1)
    print(a)
    
f()
f([])
```

    [1]
    [1]
    

函数的形参可以使用标注，标注的语法是参数后面接一个冒号 `:`，然后接一个表达式（任意表达式），通常用来指明应该（不是必须）传递什么类型的参数等。标注提高了代码的可读性：


```python
# a 标注为字符串类型，b 标注为整数，并设置默认值 2
def f(a:str,b:int=2):
    return a*b
f('Hi',3)
```




    'HiHiHi'




```python
def f(a:'字符串',b:'整数'=2):
    return a*b
f('Hi')
```




    'HiHi'


