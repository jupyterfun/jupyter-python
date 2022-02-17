## finally 清理操作

try 语句有另一个可选子句 finally，用于定义必须在所有情况下执行的清理操作（详见 [try 语句](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/10_statement/14_try.ipynb)）。

例如，在 finally 子句中关闭打开的文件：


```python
def read_file():
    try:
        f = open('../11_built-in_function/test.txt',
                encoding='utf-8')
        return f.read()
    except OSError:
        print('不能打开')
    finally:
        print('执行清理操作')
        f.close()
        
read_file() # 先执行关闭，在执行返回
```

    执行清理操作
    




    'xue.cn\n\n自学是门手艺'



如果 finally 子句中引发了新的异常，清理操作本身无效，则达不到清理目的：


```python
def read_file():
    try:
        f = open('../11_built-in_function/test.txt',
                encoding='utf-8')
        return f.read()
    except OSError:
        print('不能打开')
    finally:
        print(执行清理操作) # 清理操作引发异常
        f.close()
        
read_file() 
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-13-af7cdb6d88f0> in <module>
         10         f.close()
         11 
    ---> 12 read_file() # 先执行关闭，在执行返回
    

    <ipython-input-13-af7cdb6d88f0> in read_file()
          7         print('不能打开')
          8     finally:
    ----> 9         print(执行清理操作) # 清理操作引发异常
         10         f.close()
         11 
    

    NameError: name '执行清理操作' is not defined


某些对象（例如文件对象）定义了在不再需要该对象时，要执行的标准清理操作，无论使用该对象的操作是成功还是失败，清理操作都会被执行。此时使用 with 语句允许像文件这样的对象能够以一种确保它们得到及时和正确的清理的方式使用。

with 语句相当于将引发异常情况下的清理操作放到了 except 子句中，正常情况下的清理操作放到了 finally 子句中。详情见 [with 语句](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/10_statement/16_with.ipynb)。


```python
def read_file():
    with open('../11_built-in_function/test.txt',
                encoding='utf-8') as f:
        return f.read()
    
read_file()
```




    'xue.cn\n\n自学是门手艺'


