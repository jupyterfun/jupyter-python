## str.isupper 是大写？

字符串方法 str.isupper()，Python 官方文档描述如下：


```python
help(str.isupper)
```

    Help on method_descriptor:
    
    isupper(self, /)
        Return True if the string is an uppercase string, False otherwise.
        
        A string is uppercase if all cased characters in the string are uppercase and
        there is at least one cased character in the string.
    
    

如果字符串中至少有一个区分大小写的字符且此类字符均为大写则返回 True，否则返回 False。


```python
'Γ'.isupper()
```




    True




```python
'嗨 AB'.isupper()
```




    True




```python
'嗨 Ab'.isupper()
```




    False


