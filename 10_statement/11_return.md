## return 语句

return 在语法上只会出现于函数定义所嵌套的代码，不会出现于类定义所嵌套的代码。

如果提供了表达式，它将被求值，否则以 None 替代（类似省略 return 语句结果）。

return 会离开当前函数调用，并以表达式的值 (或 None) 作为返回值。

当 return 将控制流传出一个带有 finally 子句的 try 语句时，该 finally 子句会先被执行然后再真正离开该函数。


```python
def f2():
    x =1
print(f2())
```

    None
    


```python
def f1():
    x = 1
    return
print(f1())
```

    None
    


```python
# return 结束函数调用
def f(x):
    return x**2
    print('end') # retrun 结束函数调用，不会被执行
f(2)
```




    4




```python
# finally 总是被执行再结束函数调用
def f(x):
    try:
        return 3/x
    except ZeroDivisionError as e:
        print(e)
    finally:
        return x, x**2
f(0),f(2)
```

    division by zero
    




    ((0, 0), (2, 4))


