## str.rsplit 拆分

字符串方法 str.rsplit()，Python 官方文档描述如下：


```python
help(str.rsplit)
```

    Help on method_descriptor:
    
    rsplit(self, /, sep=None, maxsplit=-1)
        Return a list of the words in the string, using sep as the delimiter string.
        
          sep
            The delimiter according which to split the string.
            None (the default value) means split according to any whitespace,
            and discard empty strings from the result.
          maxsplit
            Maximum number of splits to do.
            -1 (the default value) means no limit.
        
        Splits are done starting at the end of the string and working to the front.
    
    

返回一个由字符串内单词组成的列表，使用 sep 作为分隔字符串。如果给出了 maxsplit，则最多进行 maxsplit 次拆分，从 最右边开始。如果 sep 未指定或为 None，任何空白字符串都会被作为分隔符。除了从右边开始拆分，rsplit() 的其他行为都类似于 split()。


```python
'p\nyth   on '.rsplit()
```




    ['p', 'yth', 'on']




```python
'p\nyth on'.rsplit('y')
```




    ['p\n', 'th on']




```python
'p\nyth on'.rsplit(maxsplit=1)
```




    ['p\nyth', 'on']




```python
'p\nyth   on '.rsplit(maxsplit=2)
```




    ['p', 'yth', 'on']



多个分隔符在一起，则会解读为拆分空字符串：


```python
'\n\np\nyth on'.rsplit('\n')
```




    ['', '', 'p', 'yth on']


