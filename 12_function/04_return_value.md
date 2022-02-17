## 函数返回值

函数返回值通过 [return 语句](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/10_statement/11_return.ipynb) 来实现，调用函数时，返回 return 语句之后表达式的值，没有 return 语句或 return 语句之后为空的函数，调用函数默认返回 None。


```python
def f(x):
    return x**2

f(2)
```




    4




```python
def f():
    pass

f() is None
```




    True



函数执行到 return 语句，则结束当前函数的调用，可以通过条件判断，返回特定结果：


```python
def f(x=None):
    if x == None:
        return 0 # 使用默认值调用函数，接下来的代码将不被执行
    print(f'x={x}') 
    if x != None:
        return f'x²={x**2}'
    
f()
```




    0




```python
f(2)
```

    x=2
    




    'x²=4'



return 之后的表达式可以是多个表达式用逗号隔开（其实是一个元组），可用赋值语句分别接收返回值：


```python
def f(x):
    return sum(x), max(x), min(x)
f([1,2,3,4])
```




    (10, 4, 1)




```python
sum_x, max_x, min_x = f([1,2,3,4])
sum_x, max_x, min_x
```




    (10, 4, 1)



返回值可以是任何值。如果 return 之后的表达式中包含函数自身的调用，则该函数称为递归函数。详见 [递归函数](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/12_function/05_recursion.ipynb)。


```python
# 返回函数自身
def f(x):
    print(x)
    return f

f(1)(2)(3)
```

    1
    2
    3
    




    <function __main__.f(x)>




```python
# 返回函数自身的调用
def f(x):
    if x == 0:
        return 0
    else:
        print(x-1)
        return f(x-1)
    
f(3)
```

    2
    1
    0
    




    0


