## str.expandtabs 替换制表符

字符串方法 str.expandtabs()，Python 官方文档描述如下：


```python
help(str.expandtabs)
```

    Help on method_descriptor:
    
    expandtabs(self, /, tabsize=8)
        Return a copy where all tab characters are expanded using spaces.
        
        If tabsize is not given, a tab size of 8 characters is assumed.
    
    

返回字符串的副本，其中所有的制表符会由一个或多个空格替换，具体取决于当前列位置和给定的制表符宽度。每 tabsize 个字符设为一个制表位（默认值 8 时设定的制表位在列 0, 8, 16 依次类推）。

要展开字符串，当前列将被设为零并逐一检查字符串中的每个字符。如果字符为制表符 (\t)，则会在结果中插入一个或多个空格符，直到当前列等于下一个制表位。（制表符本身不会被复制。）

如果字符为换行符 (\n) 或回车符 (\r)，它会被复制并将当前列重设为零。任何其他字符会被不加修改地复制并将当前列加一，不论该字符在被打印时会如何显示。


```python
'01\t012\t0123\t01234'.expandtabs()
```




    '01      012     0123    01234'




```python
'01\t012\t0123\t01234'.expandtabs(4)
```




    '01  012 0123    01234'




```python
'\n\t01\r2\t0123\t01234'.expandtabs(4)
```




    '\n    01\r2   0123    01234'


