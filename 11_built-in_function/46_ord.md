## ord() 返回单个字符 Unicode 码位值

内置函数 ord()，Python 官方文档描述如下：


```python
help(ord)
```

    Help on built-in function ord in module builtins:
    
    ord(c, /)
        Return the Unicode code point for a one-character string.
    
    

返回单个字符 Unicode 码点的整数。这是 chr() 的逆函数。


```python
ord('a')
```




    97




```python
chr(97)
```




    'a'


