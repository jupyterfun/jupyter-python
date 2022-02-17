## 函数调用

函数名之后带一个圆括号，圆括号内，根据形参的类型（详见[函数形参](xue/脚本/kp_book/12_function/03_formal_parameter.ipynb)），给函数传递相应的实参，即可调用函数，执行函数体中的代码。

函数调用传递的实参分为：**位置参数**和**关键字参数**。

- 位置参数: 调用函数时，不带标识符（例如 name=）直接按形参位置传递给函数的参数。位置参数可使用 `*` 将可迭代对象的元素拆包传入函数，但元素个数不能多于可接收位置参数的形参个数，除非有接收多个位置参数的可变位置形参。


```python
def f(a,b=None,*c,d=None):
    print(f'a={a},b={b},c={c},d={d}')
    
f(*[1,2,3,4,5]) # d 只能接收关键字参数
```

    a=1,b=2,c=(3, 4, 5),d=None
    


```python
def f(a,b=None,*,c=None):
    print(f'a={a},b={b},c={c}')
    
f(1,2)
f(1,2,3) # c 只能接收关键字参数
```

    a=1,b=2,c=None
    


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-2-9cc318bcfef7> in <module>
          2     print(f'a={a},b={b},c={c}')
          3 f(1,2)
    ----> 4 f(1,2,3)
    

    TypeError: f() takes from 1 to 2 positional arguments but 3 were given


- 关键字参数: 函数调用中前面带有标识符（例如 name=）传递给函数的参数。关键字参数可以使用 `**` 将字典里的元素传入函数，但元素个数不能多于可接收关键字参数的形参个数。关键字参数的标识符或字典的键，必须与可接收关键字参数的形参的名称相同，除非有可接收任意关键字参数的可变关键字形参。


```python
def f(a,/,b=None,*,c=None):
    print(f'a={a},b={b},c={c}')
    
f(1,c=3,b=2) # a 仅限位置传参
f(a=1,c=3,b=2)
```

    a=1,b=2,c=3
    


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-7-3c39aaeac558> in <module>
          3 
          4 f(1,c=3,b=2) # a 仅限位置传参
    ----> 5 f(a=1,c=3,b=2)
    

    TypeError: f() got some positional-only arguments passed as keyword arguments: 'a'



```python
def f(a,/,b=None,**c):
    print(f'a={a},b={b},c={c}')

# a 仅限位置，b 没有对应的名称，因此全部传给 c
f(1,**{'a':1,'d':4,'c':3})
```

    a=1,b=None,c={'a': 1, 'd': 4, 'c': 3}
    

位置参数必须在关键字参数前面：


```python
def f(a,b=None,**c):
    print(f'a={a},b={b},c={c}')

f(b=2,1)
```


      File "<ipython-input-13-59f3b615f9f3>", line 4
        f(b=2,1)
              ^
    SyntaxError: positional argument follows keyword argument
    


位置参数的位置不能传错，关键字参数的则可以任意位置：


```python
def f(a,b=None,/,c=None,**d):
    print(f'a={a},b={b},c={c},d={d}')

f(1,2,c=3,d=4)
f(2,1,d=4,c=3,e=5)
```

    a=1,b=2,c=3,d={'d': 4}
    a=2,b=1,c=3,d={'d': 4, 'e': 5}
    

标注并不影响传参规则，但按照标注传参是更明智的做法：


```python
def f(a:int,b:str='b')-> str:
    print(a*b)
    
f(2,'hi')
f(2,3)
```

    hihi
    6
    
