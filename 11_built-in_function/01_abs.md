## abs() 数字取绝对值

内置函数 abs()，Python 官方文档描述如下：


```python
help(abs)
```

    Help on built-in function abs in module builtins:
    
    abs(x, /)
        Return the absolute value of the argument.
    
    

返回一个数的绝对值，参数可以是整数、浮点数或任何实现了 `__abs__()` 的对象。如果参数是一
个复数，则返回它的模。


```python
abs(-1)
```




    1




```python
abs(-3.14)
```




    3.14




```python
abs(3+4j)
```




    5.0


