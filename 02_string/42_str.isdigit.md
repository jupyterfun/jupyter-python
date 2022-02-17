## str.isdigit 是数字？

字符串方法 str.isdigit()，Python 官方文档描述如下：


```python
help(str.isdigit)
```

    Help on method_descriptor:
    
    isdigit(self, /)
        Return True if the string is a digit string, False otherwise.
        
        A string is a digit string if all characters in the string are digits and there
        is at least one character in the string.
    
    

如果字符串中的所有字符都是数字，并且至少有一个字符，返回 True ，否则返回 False 。

数字包括十进制字符和需要特殊处理的数字，如兼容性上标数字。这包括了不能用来组成 10 进制数的数字，如 Kharosthi 数。严格地讲，数字是指属性值为 Numeric_Type=Digit 或 Numeric_Type=Decimal 的字符。


```python
'一'.isdigit()
```




    False




```python
'3.14'.isdigit()
```




    False




```python
'１２３'.isdigit()
```




    True




```python
b'123'.isdigit()
```




    True




```python
'5²'.isdigit()
```




    True


