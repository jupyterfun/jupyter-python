## str.swapcase 大小写互转

字符串方法 str.swapcase()，Python 官方文档描述如下：


```python
help(str.swapcase)
```

    Help on method_descriptor:
    
    swapcase(self, /)
        Convert uppercase characters to lowercase and lowercase characters to uppercase.
    
    

返回原字符串的副本，其中大写字符转换为小写，反之亦然。请注意 s.swapcase().swapcase() == s 并不一定为真值。


```python
'PythoN'.swapcase()
```




    'pYTHOn'




```python
'pYTHOn'.swapcase()
```




    'PythoN'




```python
'ß'.swapcase() # 德语的小写字母 ß 相当于 ss
```




    'SS'




```python
'SS'.swapcase()
```




    'ss'




```python
'ß'.swapcase().swapcase() == 'ß'
```




    False


