## str.isspace 是空白字符？

字符串方法 str.isspace()，Python 官方文档描述如下：


```python
help(str.isspace)
```

    Help on method_descriptor:
    
    isspace(self, /)
        Return True if the string is a whitespace string, False otherwise.
        
        A string is whitespace if all characters in the string are whitespace and there
        is at least one character in the string.
    
    

如果字符串中只有空白字符且至少有一个字符则返回 True，否则返回 False。


```python
''.isspace()
```




    False




```python
' '.isspace()
```




    True




```python
'\n\t\r\f'.isspace()
```




    True




```python
' \\'.isspace()
```




    False


