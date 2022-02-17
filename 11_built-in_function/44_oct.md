## oct() 整数的八进制形式

内置函数 oct()，Python 官方文档描述如下：


```python
help(oct)
```

    Help on built-in function oct in module builtins:
    
    oct(number, /)
        Return the octal representation of an integer.
        
        >>> oct(342391)
        '0o1234567'
    
    

将一个整数转换为八进制整数的字符串形式。


```python
oct(123)
```




    '0o173'




```python
0o173
```




    123




```python
oct(0x12)
```




    '0o22'




```python
0x12, 0o22
```




    (18, 18)


