## str.lstrip 移除左边字符

字符串方法 str.lstrip()，Python 官方文档描述如下：


```python
help(str.lstrip)
```

    Help on method_descriptor:
    
    lstrip(self, chars=None, /)
        Return a copy of the string with leading whitespace removed.
        
        If chars is given and not None, remove characters in chars instead.
    
    

返回原字符串的副本，移除其中的前导字符。chars 参数为指定要移除字符的字符串。如果省略或为 None，则 chars 参数默认移除空格符。实际上 chars 参数并非指定单个前缀；而是会移除参数值中出现的所有字符:


```python
'  python  '.lstrip()
```




    'python  '




```python
'  python  '.lstrip('y p')
```




    'thon  '




```python
'  python  '.lstrip('py')
```




    '  python  '




```python
'ppppython  '.lstrip('y p')
```




    'thon  '


