## str.istitle 是标题字符串？

字符串方法 str.istitle()，Python 官方文档描述如下：


```python
help(str.istitle)
```

    Help on method_descriptor:
    
    istitle(self, /)
        Return True if the string is a title-cased string, False otherwise.
        
        In a title-cased string, upper- and title-case characters may only
        follow uncased characters and lowercase characters only cased ones.
    
    

如果字符串中至少有一个字符且为标题字符串则返回 True，例如大写字符之后只能带非大写字符而小写字符必须有大写字符打头。否则返回 False。


```python
'Abc Py'.istitle()
```




    True




```python
'嗨 A11'.istitle()
```




    True




```python
'嗨 Abc'.istitle()
```




    True




```python
'嗨 ABC'.istitle()
```




    False


