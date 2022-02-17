## str.isascii 是 ASCII 字符？

字符串方法 str.isascii()，Python 官方文档描述如下：


```python
help(str.isascii)
```

    Help on method_descriptor:
    
    isascii(self, /)
        Return True if all characters in the string are ASCII, False otherwise.
        
        ASCII characters have code points in the range U+0000-U+007F.
        Empty string is ASCII too.
    
    

如果字符串为空或字符串中的所有字符都是 ASCII ，返回 True，否则返回 False。ASCII 字符的码点范围是 U+0000-U+007F。


```python
''.isascii()
```




    True




```python
'python'.isascii()
```




    True




```python
'python.3'.isascii()
```




    True




```python
'嗨 python'.isascii()
```




    False


