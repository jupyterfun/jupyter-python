## 函数文档

关键字 def 引入一个函数定义。构成函数体的语句从下一行开始，并且必须缩进。

函数体的第一个语句可以是字符串文字（可选的），这个字符串文字即是函数的文档字符串。有些工具使用文档字符串自动生成在线或印刷文档，或者让用户以交互式的形式浏览代码。在你编写的代码中包含文档字符串是一种很好的做法，所以要养成习惯。

文档字符串的内容和格式的约定：
- 第一行应该是函数目的的简要概述。为简洁起见，它不应显式声明对象的名称或类型，因为这些可通过其他方式获得（除非名称恰好是描述函数操作的动词）。这一行应以大写字母开头，以句点结尾。

- 如果文档字符串中有更多行，则第二行应为空白，从而在视觉上将摘要与其余描述分开。后面几行应该是一个或多个段落，描述对象的调用约定，它的副作用等。

可以使用函数的 `__doc__` 属性或 help() 函数查看函数文档。


```python
help(my_function)
```

    Help on function my_function in module __main__:
    
    my_function()
        Do nothing, but document it.
    
    


```python
def my_function():
    'Do nothing, but document it.'
    pass

my_function.__doc__
```




    'Do nothing, but document it.'




```python
# 多行的函数文档
def my_func():
    """Do nothing, but document it.

    No, really, it doesn't do anything.
    """
    pass
print(my_func.__doc__)
```

    Do nothing, but document it.
    
        No, really, it doesn't do anything.
        
    


```python
help(my_func)
```

    Help on function my_func in module __main__:
    
    my_func()
        Do nothing, but document it.
        
        No, really, it doesn't do anything.
    
    


```python
print(print.__doc__)
```

    print(value, ..., sep=' ', end='\n', file=sys.stdout, flush=False)
    
    Prints the values to a stream, or to sys.stdout by default.
    Optional keyword arguments:
    file:  a file-like object (stream); defaults to the current sys.stdout.
    sep:   string inserted between values, default a space.
    end:   string appended after the last value, default a newline.
    flush: whether to forcibly flush the stream.
    
