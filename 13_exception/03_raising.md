## 抛出异常

[raise 语句](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/10_statement/15_raise.ipynb) 允许强制发生指定的异常。


```python
raise NameError('HiThere')
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-1-72c183edb298> in <module>
    ----> 1 raise NameError('HiThere')
    

    NameError: HiThere


如果你需要确定是否引发了异常但不打算处理它，则可以使用更简单的 raise 语句形式重新引发异常:


```python
try:
    raise NameError('HiThere')
except NameError:
    print('An exception flew by!')
    raise
```

    An exception flew by!
    


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-2-bf6ef4926f8c> in <module>
          1 try:
    ----> 2     raise NameError('HiThere')
          3 except NameError:
          4     print('An exception flew by!')
          5     raise
    

    NameError: HiThere

