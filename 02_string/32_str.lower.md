## str.lower 转小写

字符串方法 str.lower()，Python 官方文档描述如下：


```python
help(str.lower)
```

    Help on method_descriptor:
    
    lower(self, /)
        Return a copy of the string converted to lowercase.
    
    

返回原字符串的副本，其所有区分大小写的字符均转换为小写。


```python
'PyThon'.lower()
```




    'python'




```python
'嗨 PyThon'.lower()
```




    '嗨 python'




```python
'PyThon Γ'.lower()
```




    'python γ'


