## hex() 整数的十六进制形式

内置函数 hex()，Python 官方文档描述如下：


```python
help(hex)
```

    Help on built-in function hex in module builtins:
    
    hex(number, /)
        Return the hexadecimal representation of an integer.
        
        >>> hex(12648430)
        '0xc0ffee'
    
    

将整数转换为以 `0x` 为前缀的小写十六进制整数的字符串形式。


```python
hex(123)
```




    '0x7b'




```python
0x7b
```




    123


