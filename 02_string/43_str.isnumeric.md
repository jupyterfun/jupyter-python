## str.isnumeric 是数值字符？

字符串方法 str.isnumeric()，Python 官方文档描述如下：


```python
help(str.isnumeric)
```

    Help on method_descriptor:
    
    isnumeric(self, /)
        Return True if the string is a numeric string, False otherwise.
        
        A string is numeric if all characters in the string are numeric and there is at
        least one character in the string.
    
    

如果字符串中至少有一个字符且所有字符均为数值字符则返回 True，否则返回 False。

数值字符包括数字字符，以及所有在 Unicode 中设置了数值特性属性的字符，例如 U+2155, VUL-GAR FRACTION ONE FIFTH。正式的定义为：数值字符就是具有特征属性值 Numeric_Type=Digit, Numeric_Type=Decimal 或 Numeric_Type=Numeric 的字符。

此处所指数字包括罗马数字，汉字数字等。


```python
'②'.isnumeric()
```




    True




```python
'3.14'.isnumeric()
```




    False




```python
'5²'.isnumeric()
```




    True




```python
'Ⅷ'.isnumeric()
```




    True




```python
'一'.isnumeric()
```




    True




```python
'壹'.isnumeric()
```




    True


