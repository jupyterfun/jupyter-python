## 函数定义

函数定义有两种方式，def 语句定义有名字的函数（详见 [def 定义函数](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/10_statement/10_def.ipynb)），lambda 表达式定义匿名函数（详见 [lambda 函数](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/12_function/08_lambda.ipynb)）。

定义一个函数，即是创建了一个函数可执行代码的包装器，他将函数想要实现的功能包装起来。然后通过调用它来实现其功能。def 语句 详细介绍了定义函数的语法规则，下面看看如何将一个功能包装起来。

例如下列函数，实现了将列表中的 字符串整数 以及 整数 相加求和的功能，以后只要遇到这种情况，都可以用它来求和：


```python
sumpro([1,'2','3'])
```




    6




```python
# def 定义
def sumpro(lst):
    return sum(int(i) for i in lst)
```


```python
sumpro(['1 ',' 2',3])
```




    6




```python
# lambda 表达式定义
lambda lst: sum(int(i) for i in lst)
```




    <function __main__.<lambda>(lst)>




```python
lst = [['2','8'],['3','4']]
sorted(lst,key=lambda lst: sum(int(i) for i in lst))
```




    [['3', '4'], ['2', '8']]



函数定义，也可以定义为实现功能，但没有返回值（默认返回 None）的过程。

例如下列函数，实现了将列表中的字符串整数都转换为整数：


```python
def convert_to_numb(lst):
    for i in range(len(lst)):
        if type(lst[i]) != int:
            lst[i] = int(lst[i])
```


```python
lst = ['1',2,'3']
n = convert_to_numb(lst)
lst, n is None
```




    ([1, 2, 3], True)



函数定义所使用的函数名称，不能与当前作用域中以定义的名称相同，这会屏蔽掉已存在的名称，或将自定义的函数对象重新赋值给了该名称。


```python
str(123)
```




    '123'




```python
def str(x):
    return f'x={x}'
str(123) # 屏蔽掉了内置名称 str
```




    'x=123'




```python
f = 0
def f():
    pass
f # f 被重新赋值
```




    <function __main__.f()>


