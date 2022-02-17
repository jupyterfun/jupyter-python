## str.rpartition 拆分

字符串方法 str.rpartition()，Python 官方文档描述如下：


```python
help(str.rpartition)
```

    Help on method_descriptor:
    
    rpartition(self, sep, /)
        Partition the string into three parts using the given separator.
        
        This will search for the separator in the string, starting at the end. If
        the separator is found, returns a 3-tuple containing the part before the
        separator, the separator itself, and the part after it.
        
        If the separator is not found, returns a 3-tuple containing two empty strings
        and the original string.
    
    

在 sep 最后一次出现的位置拆分字符串，返回一个 3 元组，其中包含分隔符之前的部分、分隔符本身，以及分隔符之后的部分。如果分隔符未找到，则返回的 3 元组中包含两个空字符串以及字符串本身。


```python
'python'.rpartition('n')
```




    ('pytho', 'n', '')




```python
'pythhhon'.rpartition('hh')
```




    ('pyth', 'hh', 'on')



分隔符未找到，则返回的 3 元组中 字符串本身 排在最后：


```python
'python'.rpartition('ht') 
```




    ('', '', 'python')


