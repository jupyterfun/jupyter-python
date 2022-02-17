## str.capitalize 首字符大写

字符串方法 str.capitalize()，Python 官方文档描述如下：


```python
help(str.capitalize)
```

    Help on method_descriptor:
    
    capitalize(self, /)
        Return a capitalized version of the string.
        
        More specifically, make the first character have upper case and the rest lower
        case.
    
    

返回原字符串的副本，其首个字符大写，其余为小写:


```python
'pyTHON'.capitalize()
```




    'Python'



只有首个字符是字母，才会将首个字符大写：


```python
'嗨 pyTHON'.capitalize()
```




    '嗨 python'


