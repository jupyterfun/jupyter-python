## str.partition 拆分

字符串方法 str.partition()，Python 官方文档描述如下：


```python
help(str.partition)
```

    Help on method_descriptor:
    
    partition(self, sep, /)
        Partition the string into three parts using the given separator.
        
        This will search for the separator in the string.  If the separator is found,
        returns a 3-tuple containing the part before the separator, the separator
        itself, and the part after it.
        
        If the separator is not found, returns a 3-tuple containing the original string
        and two empty strings.
    
    

在 sep 首次出现的位置拆分字符串，返回一个 3 元组，其中包含分隔符之前的部分、分隔符本身，以及分隔符之后的部分。如果分隔符未找到，则返回的 3 元组中包含字符本身以及两个空字符串。


```python
'python'.partition('m')
```




    ('python', '', '')




```python
'python'.partition('th')
```




    ('py', 'th', 'on')




```python
'python'.partition('ht')
```




    ('python', '', '')


