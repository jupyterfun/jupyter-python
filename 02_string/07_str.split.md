## str.split 拆分

字符串方法 str.split()，Python 官方文档描述如下：


```python
help(str.split)
```

    Help on method_descriptor:
    
    split(self, /, sep=None, maxsplit=-1)
        Return a list of the words in the string, using sep as the delimiter string.
        
        sep
          The delimiter according which to split the string.
          None (the default value) means split according to any whitespace,
          and discard empty strings from the result.
        maxsplit
          Maximum number of splits to do.
          -1 (the default value) means no limit.
    
    

返回一个由字符串内单词组成的列表，使用 sep 作为分隔字符串。如果给出了 sep，则连续的分隔符不会被组合在一起而是被视为分隔空字符串；如果给出了 maxsplit，则最多进行 maxsplit 次拆分（因此，列表最多会有 maxsplit+1 个元素）。如果 maxsplit 未指定或为 -1，则不限制拆分次数（进行所有可能的拆分）。


```python
'a.bc'.split('.')
```




    ['a', 'bc']




```python
'a.b.c'.split('.',maxsplit=1)
```




    ['a', 'b.c']




```python
'a.b..c'.split('.')
```




    ['a', 'b', '', 'c']




```python
'a.b..c'.split('..')
```




    ['a.b', 'c']




```python
''.split('.')
```




    ['']



如果 sep 未指定或为 None，则会应用另一种拆分算法：连续的空格会被视为单个分隔符，如果字符串包含前缀或后缀空格，其结果将不包含开头或末尾的空字符串。因此，使用 None 拆分空字符串或仅包含空格的字符串将返回 []。


```python
'a b  c '.split()
```




    ['a', 'b', 'c']




```python
'  \n '.split()
```




    []




```python
''.split()
```




    []


