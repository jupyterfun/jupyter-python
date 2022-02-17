## def 定义函数

def 语句是定义函数的语句。语法如下：
```
@assignment_expression
def funcname(parameter_list) -> expression:
    suite
```

其中的装饰器 `@assignment_expression`，形参 `parameter_list` 和标注 `-> expression` 是可选项。

函数定义是一条可执行语句。它执行时会将函数名称 `funcname` 绑定到一个函数对象（函数可执行代码的包装器）。

例如，用必选项定义一个什么也不做的函数如下：


```python
def f():
    pass

f
```




    <function __main__.f()>



一个函数定义可以被一个或多个装饰器表达式所包装。

装饰器必须是可调用对象，它会以该函数对象作为唯一参数被发起调用。

其返回值将被绑定到函数名称。多个装饰器会以嵌套方式被应用。


```python
@str
@type
def f():pass
f
```




    "<class 'function'>"



大致相当于：


```python
def f():pass
f = str(type(f))
f
```




    "<class 'function'>"



函数形参 `parameter_list` 详见 [函数形参](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/12_function/03_formal_parameter.ipynb)。

函数标注 `-> expression` 可以是任何表达式，标注对提高代码的可读性非常有用，看标注而不需要看代码上下文就大概知道代码的使用。例如：


```python
# 标注函数的参数和返回值类型
def f(arg:int) -> list:
    return list(str(arg))
f(123)
```




    ['1', '2', '3']


