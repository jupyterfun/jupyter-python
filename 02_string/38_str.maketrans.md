## str.maketrans 生成转换表

字符串方法 str.maketrans()，该方法是一个静态方法（没有 self），Python 官方文档描述如下：


```python
help(str.maketrans)
```

    Help on built-in function maketrans:
    
    maketrans(x, y=None, z=None, /)
        Return a translation table usable for str.translate().
        
        If there is only one argument, it must be a dictionary mapping Unicode
        ordinals (integers) or characters to Unicode ordinals, strings or None.
        Character keys will be then converted to ordinals.
        If there are two arguments, they must be strings of equal length, and
        in the resulting dictionary, each character in x will be mapped to the
        character at the same position in y. If there is a third argument, it
        must be a string, whose characters will be mapped to None in the result.
    
    

返回一个可供 str.translate() 使用的转换对照表。

如果只有一个参数，则它必须是一个将 Unicode 码位序号（整数）或字符（长度为 1 的字符串）映射到 Unicode 码位序号、（任意长度的）字符串 或 None 的字典。字符键将会被转换为码位序号。


```python
str.maketrans({97:'123'})
```




    {97: '123'}




```python
str.maketrans({'a':97})
```




    {97: 97}




```python
str.maketrans({'a':None})
```




    {97: None}



如果有两个参数，则它们必须是两个长度相等的字符串，并且在结果字典中，x 中每个字符将被映射到 y 中相同位置的字符。


```python
str.maketrans('abc','123')
```




    {97: 49, 98: 50, 99: 51}



如果有第三个参数，它必须是一个字符串，其中的字符将在结果中被映
射到 None。


```python
str.maketrans('ab','12','xy')
```




    {97: 49, 98: 50, 120: None, 121: None}


