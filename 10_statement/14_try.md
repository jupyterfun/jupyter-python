## try 语句

try 语句可为一组语句指定异常处理器和/或清理代码。语法结构有两种如下。

- 有 try 和 except 子句（可多个），以及可选的 else 和 finally 子句：
```
try:
    suite
except expression as identifier:
    suite
else: # 可选
    suite
finally: # 可选
    suite
```

- 只有 try 和 finally 子句：
```
try:
    suite
finally:
    suite
```

except 子句之后的表达式（通常为异常）`expression`，关键字 `as` 以及指定的别名 `identifier` 都是可选的。

当 try 子句中没有发生异常时，没有异常处理器会被执行。当 try 子句中发生异常时，将启动对异常处理器的搜索。此搜索会依次检查 except 子句，直至找到与该异常相匹配的子句。

except 子句可指定一个或多个异常，如果与发生的异常 “兼容” 则该子句将匹配该异常。
- 指定的异常如果是发生的异常所属的类或基类，则该子句将匹配该异常；
- 指定的异常可以置于一个元组，其中包含有与发生的异常 “兼容” 的异常，该子句将匹配该异常。

当一个异常完全未被处理时，解释器会终止程序的执行。


```python
for i in range(3):
    try:
        print(3/i)
    except (ZeroDivisionError, AssertionError) as e:
        print(e)
```

    division by zero
    3.0
    1.5
    


```python
for i in range(3):
    try:
        print(3/i)
    except ZeroDivisionError:
        print(f'i={i}引发异常')
```

    i=0引发异常
    3.0
    1.5
    


```python
for i in range(3):
    print(3/i)
```


    ---------------------------------------------------------------------------

    ZeroDivisionError                         Traceback (most recent call last)

    <ipython-input-5-ddbcfc1a1b1b> in <module>
          1 for i in range(3):
    ----> 2     print(3/i)
    

    ZeroDivisionError: division by zero


如果存在无表达式的 except 子句，它必须是最后一个，它将匹配任何异常：


```python
try:
    3/0
except NameError as n:
    print(n)
except:
    pass
```

如果没有 except 子句与异常相匹配，则会在周边代码和发起调用栈上继续搜索异常处理器，除非存在一个finally 子句正好引发了另一个异常。新引发的异常将导致旧异常的丢失:


```python
def f():
    try:
        return 3/0
    except NameError as n:
        print(n)
try:
    f()
except ZeroDivisionError as z:
    print(z)
```

    division by zero
    


```python
def f():
    try:
        return 3/0
    except NameError as n:
        print(n)
    finally:
        name1
        
try:
    f()
except ZeroDivisionError as z: # 该异常已丢失
    print(z)
except NameError as n:
    print(n)
```

    name 'name1' is not defined
    

使用 as 将匹配的异常赋值给一个别名，才能在 except 子句之后引用它，并且它将在 except 子句结束时被清除：


```python
for i in range(3):
    try:
        print(3/i)
    except (ZeroDivisionError, AssertionError) as e:
        print(e)
print(e)
```

    division by zero
    3.0
    1.5
    


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-16-a87e190baccb> in <module>
          4     except (ZeroDivisionError, AssertionError) as e:
          5         print(e)
    ----> 6 print(e)
    

    NameError: name 'e' is not defined


如果控制流离开 try 子句体时没有引发异常，并且没有执行 return, continue 或 break 语句，可选的 else 子句将被执行:


```python
try:
    print('开始')
except:
    print('捕获')
else:
    print('结束')
```

    开始
    结束
    


```python
while True:    
    try:
        print('开始')
        break
    except:
        print('捕获')
    else:
        print('结束')
```

    开始
    

如果存在 finally，它用来指定一个 “清理” 处理程序。try，except 或 else 子句中发生任何未处理的异常，会被临时保存。finally 始终被执行，被保存的异常，它会在 finally 子句执行后被重新引发：


```python
try:
    print(3/0)
except:
    name2
else: # 未被执行
    range(3)[5]
finally:
    print('end')
```

    end
    


    ---------------------------------------------------------------------------

    ZeroDivisionError                         Traceback (most recent call last)

    <ipython-input-24-7d6fe0d94043> in <module>
          1 try:
    ----> 2     print(3/0)
          3 except:
    

    ZeroDivisionError: division by zero

    
    During handling of the above exception, another exception occurred:
    

    NameError                                 Traceback (most recent call last)

    <ipython-input-24-7d6fe0d94043> in <module>
          2     print(3/0)
          3 except:
    ----> 4     name2
          5 else: # 未被执行
          6     range(3)[5]
    

    NameError: name 'name2' is not defined


如果 finally 子句引发了另一个异常，被保存的异常会被设为新异常的上下文。如果 finally 子句执行了 return, break 或 continue 语句，则被保存的异常会被丢弃:


```python
while True:    
    try:
        print('开始')
    except:
        print('捕获')
    else:
        range(3)[5]
    finally:
        print(3/0)
```

    开始
    


    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    <ipython-input-25-1f272bfbd667> in <module>
          6     else:
    ----> 7         range(3)[5]
          8     finally:
    

    IndexError: range object index out of range

    
    During handling of the above exception, another exception occurred:
    

    ZeroDivisionError                         Traceback (most recent call last)

    <ipython-input-25-1f272bfbd667> in <module>
          7         range(3)[5]
          8     finally:
    ----> 9         print(3/0)
    

    ZeroDivisionError: division by zero



```python
while True:    
    try:
        print('开始')
    except:
        print('捕获')
    else:
        range(3)[5]
    finally:
        break
```

    开始
    

当 return, break 或 continue 语句在 finally 语句之前被执行时，finally 子语句也会 ‘在离开时’ 被执行:


```python
while True:    
    try:
        print('开始')
    except:
        print('捕获')
    else:
        break
    finally:
        print('结束')
```

    开始
    结束
    


```python
def f():    
    try:
        return '开始'
    finally:
        print('结束')
f() # 先执行 finally 再离开函数调用
```

    结束
    




    '开始'


