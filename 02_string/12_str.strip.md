## str.strip 移除两边字符

字符串方法 str.strip()，Python 官方文档描述如下：


```python
help(str.strip)
```

    Help on method_descriptor:
    
    strip(self, chars=None, /)
        Return a copy of the string with leading and trailing whitespace remove.
        
        If chars is given and not None, remove characters in chars instead.
    
    

返回原字符串的副本，移除其中的前导和末尾字符。chars 参数为指定要移除字符的字符串。如果省略或为 None，则 chars 参数默认移除空格符。实际上 chars 参数并非指定单个前缀或后缀；而是会移除参数值中的所有字符:


```python
' python '.strip()
```




    'python'




```python
' python '.strip('p')
```




    ' python '




```python
' python '.strip('p n')
```




    'ytho'




```python
' pythonnnn '.strip('p n')
```




    'ytho'


