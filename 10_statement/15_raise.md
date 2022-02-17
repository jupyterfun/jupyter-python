## raise 语句

raise 语句用来引发异常。语法如下：
```
raise expression from expression
```

如果不带表达式，raise 会重新引发当前作用域内最后一个激活的异常。如果当前作用域内没有激活的异常，将会引发 RuntimeError 来提示错误。


```python
raise
```


    ---------------------------------------------------------------------------

    RuntimeError                              Traceback (most recent call last)

    <ipython-input-1-9c9a2cba73bf> in <module>
    ----> 1 raise
    

    RuntimeError: No active exception to reraise


raise 会将第一个表达式求值为异常对象。它必须为 BaseException 的子类或实例。如果它是一个类，当需要时会通过不带参数地实例化该类来获得异常的实例。


```python
type(ZeroDivisionError)
```




    type




```python
raise ZeroDivisionError # 无提示信息
```


    ---------------------------------------------------------------------------

    ZeroDivisionError                         Traceback (most recent call last)

    <ipython-input-2-798b08d1683c> in <module>
    ----> 1 raise ZeroDivisionError # 无提示信息
    

    ZeroDivisionError: 



```python
raise ZeroDivisionError('分母不能为 0') # 自定义提示信息
```


    ---------------------------------------------------------------------------

    ZeroDivisionError                         Traceback (most recent call last)

    <ipython-input-17-950b4accf1f2> in <module>
    ----> 1 raise ZeroDivisionError('分母不能为 0') # 自定义提示信息
    

    ZeroDivisionError: 分母不能为 0


from 子句用于异常串连：如果有该子句，则第二个表达式必须为另一个异常类或实例，它将被关联到所引发的异常:


```python
raise IndexError("索引错误") from NameError('名称错误')
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    NameError: 名称错误

    
    The above exception was the direct cause of the following exception:
    

    IndexError                                Traceback (most recent call last)

    <ipython-input-18-124f83b49e6f> in <module>
    ----> 1 raise IndexError("索引错误") from NameError('名称错误')
    

    IndexError: 索引错误



```python
try:
    print(1 / 0)
except Exception as e:
    raise RuntimeError("Something bad happened") from e
```


    ---------------------------------------------------------------------------

    ZeroDivisionError                         Traceback (most recent call last)

    <ipython-input-13-83aaca0b7e7f> in <module>
          1 try:
    ----> 2     print(1 / 0)
          3 except Exception as e:
    

    ZeroDivisionError: division by zero

    
    The above exception was the direct cause of the following exception:
    

    RuntimeError                              Traceback (most recent call last)

    <ipython-input-13-83aaca0b7e7f> in <module>
          2     print(1 / 0)
          3 except Exception as e:
    ----> 4     raise RuntimeError("Something bad happened") from e
    

    RuntimeError: Something bad happened


如果一个异常在异常处理器或 finally 中被引发，类似的机制会隐式地发挥作用：


```python
try:
    print(1 / 0)
except:
    raise RuntimeError("Something bad happened")
```


    ---------------------------------------------------------------------------

    ZeroDivisionError                         Traceback (most recent call last)

    <ipython-input-16-5576c5c08e42> in <module>
          1 try:
    ----> 2     print(1 / 0)
          3 except:
    

    ZeroDivisionError: division by zero

    
    During handling of the above exception, another exception occurred:
    

    RuntimeError                              Traceback (most recent call last)

    <ipython-input-16-5576c5c08e42> in <module>
          2     print(1 / 0)
          3 except:
    ----> 4     raise RuntimeError("Something bad happened")
    

    RuntimeError: Something bad happened



```python
try:
    print(1 / 0)
finally:
    raise RuntimeError("Something bad happened")
```


    ---------------------------------------------------------------------------

    ZeroDivisionError                         Traceback (most recent call last)

    <ipython-input-15-8b172672db5a> in <module>
          1 try:
    ----> 2     print(1 / 0)
          3 finally:
    

    ZeroDivisionError: division by zero

    
    During handling of the above exception, another exception occurred:
    

    RuntimeError                              Traceback (most recent call last)

    <ipython-input-15-8b172672db5a> in <module>
          2     print(1 / 0)
          3 finally:
    ----> 4     raise RuntimeError("Something bad happened")
    

    RuntimeError: Something bad happened

