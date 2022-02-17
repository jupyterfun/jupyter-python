## str.ljust 左对齐

字符串方法 str.ljust()，Python 官方文档描述如下：


```python
help(str.ljust)
```

    Help on method_descriptor:
    
    ljust(self, width, fillchar=' ', /)
        Return a left-justified string of length width.
        
        Padding is done using the specified fill character (default is a space).
    
    

返回长度为 width 的字符串，原字符串在其中靠左对齐。使用指定的 fillchar 填充空位 (默认使用 ASCII 空格符)。如果 width 小于等于字符串长度 len(str) 则返回原字符串的副本。


```python
'python'.ljust(1)
```




    'python'




```python
'python'.ljust(10,'~')
```




    'python~~~~'




```python
'python'.ljust(10)
```




    'python    '


