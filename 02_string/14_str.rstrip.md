## str.rstrip 移除右边字符

字符串方法 str.rstrip()，Python 官方文档描述如下：


```python
help(str.rstrip)
```

    Help on method_descriptor:
    
    rstrip(self, chars=None, /)
        Return a copy of the string with trailing whitespace removed.
        
        If chars is given and not None, remove characters in chars instead.
    
    

返回原字符串的副本，移除其中的末尾字符。chars 参数为指定要移除字符的字符串。如果省略或为 None，则 chars 参数默认移除空格符。实际上 chars 参数并非指定单个后缀；而是会移除参数值中的所有字符串:


```python
' python '.rstrip()
```




    ' python'




```python
' python '.rstrip('n o')
```




    ' pyth'




```python
' python '.rstrip('n')
```




    ' python '




```python
' pythonnnnn'.rstrip('no')
```




    ' pyth'


