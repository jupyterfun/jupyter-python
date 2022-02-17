## assert 语句

assert 语句是在程序中插入调试性断言的简便方式。在表达式条件为 False 的时候触发异常。

简单形式为：`assert expression`。


```python
assert 1 + 1 == 2
```


```python
assert 1 + 1 != 2
```


    ---------------------------------------------------------------------------

    AssertionError                            Traceback (most recent call last)

    <ipython-input-2-5cd89e6dd50b> in <module>
    ----> 1 assert 1 + 1 != 2
    

    AssertionError: 


扩展形式为：`assert expression1, expression2`。expression2 通常是提示信息。


```python
assert 1 + 1 != 2, '计算错误'
```


    ---------------------------------------------------------------------------

    AssertionError                            Traceback (most recent call last)

    <ipython-input-7-3b85a53ff241> in <module>
    ----> 1 assert 1 + 1 != 2, '计算错误'
    

    AssertionError: 计算错误



```python
for i in range(5):
    try:
        assert i % 2 == 0, f'{i}是奇数'
        print(i)
    except AssertionError as a:
        print(a)
```

    0
    1是奇数
    2
    3是奇数
    4
    
