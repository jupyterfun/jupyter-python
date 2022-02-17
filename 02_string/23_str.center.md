## str.center 居中

字符串方法 str.center()，Python 官方文档描述如下：


```python
help(str.center)
```

    Help on method_descriptor:
    
    center(self, width, fillchar=' ', /)
        Return a centered string of length width.
        
        Padding is done using the specified fill character (default is a space).
    
    

返回长度为 width 的字符串，原字符串在其正中。使用指定的 fillchar 填充两边的空位（默认使用ASCII 空格符）。如果 width 小于等于字符串长度，则返回原字符串的副本:


```python
'Python'.center(1)
```




    'Python'




```python
'Python'.center(10)
```




    '  Python  '




```python
'Python'.center(20,'~')
```




    '~~~~~~~Python~~~~~~~'


