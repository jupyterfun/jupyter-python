## str.casefold 消除大小写

字符串方法 str.casefold()，Python 官方文档描述如下：


```python
help(str.casefold)
```

    Help on method_descriptor:
    
    casefold(self, /)
        Return a version of the string suitable for caseless comparisons.
    
    

返回原字符串消除大小写的副本。消除大小写的字符串可用于忽略大小写的匹配。

消除大小写类似于转为小写，但是更加彻底一些，因为它会移除字符串中的所有大小写变化形式。例如，德语小写字母 'ß' 相当于 "ss"，由于它已经是小写，lower() 不会对 'ß' 做任何改变，而 casefold() 则会将其转换为 "ss"。


```python
'pYthOn'.casefold()
```




    'python'




```python
'ß'.casefold()
```




    'ss'




```python
'ß'.lower()
```




    'ß'


