## str.islower 是小写？

字符串方法 str.islower()，Python 官方文档描述如下：


```python
help(str.islower)
```

    Help on method_descriptor:
    
    islower(self, /)
        Return True if the string is a lowercase string, False otherwise.
        
        A string is lowercase if all cased characters in the string are lowercase and
        there is at least one cased character in the string.
    
    

如果字符串中至少有一个区分大小写的字符且此类字符均为小写则返回 True，否则返回 False。


```python
'嗨'.islower()
```




    False




```python
'嗨 Abc'.islower()
```




    False




```python
'嗨 abc'.islower()
```




    True


