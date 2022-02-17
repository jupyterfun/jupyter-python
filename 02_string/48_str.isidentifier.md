## str.isidentifier 是有效标识符？

字符串方法 str.isidentifier()，Python 官方文档描述如下：


```python
help(str.isidentifier)
```

    Help on method_descriptor:
    
    isidentifier(self, /)
        Return True if the string is a valid Python identifier, False otherwise.
        
        Call keyword.iskeyword(s) to test whether string s is a reserved identifier,
        such as "def" or "class".
    
    

如果字符串是有效的标识符，返回 True，否则返回 False。


```python
''.isidentifier()
```




    False




```python
'1mycode'.isidentifier()
```




    False




```python
'_mycode'.isidentifier()
```




    True




```python
'123'.isidentifier()
```




    False




```python
'_123'.isidentifier()
```




    True




```python
'变量名'.isidentifier()
```




    True




```python
'for'.isidentifier()
```




    True


