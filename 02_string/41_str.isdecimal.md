## str.isdecimal 是十进制字符？

字符串方法 str.isdecimal()，Python 官方文档描述如下：


```python
help(str.isdecimal)
```

    Help on method_descriptor:
    
    isdecimal(self, /)
        Return True if the string is a decimal string, False otherwise.
        
        A string is a decimal string if all characters in the string are decimal and
        there is at least one character in the string.
    
    

如果字符串中的所有字符都是十进制字符且该字符串至少有一个字符，则返回 True，否则返回 False。

十进制字符指那些可以用来组成 10 进制数字的字符。严格地讲，十进制字符是 Unicode 通用类别 ”Nd” 中的一个字符。


```python
''.isdecimal()
```




    False




```python
'3.14'.isdecimal()
```




    False




```python
'０1２3'.isdecimal()
```




    True




```python
'5²'.isdecimal()
```




    False




```python
'python'.isdecimal()
```




    False




```python
b'100'.isdecimal()
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-13-52e1682babfd> in <module>
    ----> 1 b'100'.isdecimal()
    

    AttributeError: 'bytes' object has no attribute 'isdecimal'

