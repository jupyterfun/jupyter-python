## ascii() 返回对象的可打印字符串

内置函数 ascii()，Python 官方文档描述如下：


```python
help(ascii)
```

    Help on built-in function ascii in module builtins:
    
    ascii(obj, /)
        Return an ASCII-only representation of an object.
        
        As repr(), return a string containing a printable representation of an
        object, but escape the non-ASCII characters in the string returned by
        repr() using \\x, \\u or \\U escapes. This generates a string similar
        to that returned by repr() in Python 2.
    
    

就像函数 repr()，返回一个对象可打印的字符串，但是非 ASCII 编码的字符，会使用 \x、\u 和 \U 来转义。


```python
ascii(123)
```




    '123'




```python
ascii(None)
```




    'None'




```python
ascii('python')
```




    "'python'"




```python
ascii('嗨')
```




    "'\\u55e8'"




```python
repr('嗨')
```




    "'嗨'"




```python
'\u55e8' # 16 位十六进制数 55e8 码位的字符
```




    '嗨'


