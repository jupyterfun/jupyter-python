## chr() 返回 Unicode 码位值对应字符

内置函数 chr()，Python 官方文档描述如下：


```python
help(chr)
```

    Help on built-in function chr in module builtins:
    
    chr(i, /)
        Return a Unicode string of one character with ordinal i; 0 <= i <= 0x10ffff.
    
    

返回 Unicode 码位对应的字符的字符串格式。码位范围是 0~1114111（16 进制表示是 0x10FFFF），超过这个范围，会触发 ValueError 异常。该函数是 ord() 的逆函数。


```python
chr(97)
```




    'a'




```python
ord('a')
```




    97




```python
chr(1114111)
```




    '\U0010ffff'




```python
chr(1114112)
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-5-4857faf08086> in <module>
    ----> 1 chr(1114112)
    

    ValueError: chr() arg not in range(0x110000)

