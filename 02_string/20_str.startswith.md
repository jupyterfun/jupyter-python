## str.startswith 指定字符串开头？

字符串方法 str.startswith()，Python 官方文档描述如下：


```python
help(str.startswith)
```

    Help on method_descriptor:
    
    startswith(...)
        S.startswith(prefix[, start[, end]]) -> bool
        
        Return True if S starts with the specified prefix, False otherwise.
        With optional start, test S beginning at that position.
        With optional end, stop comparing S at that position.
        prefix can also be a tuple of strings to try.
    
    

如果字符串以指定的 prefix 开始则返回 True，否则返回 False。prefix 也可以为由多个供查找的前缀构成的元组。如果有可选项 start，将从所指定位置开始检查。如果有可选项 end，将在所指定位置之前停止比较。


```python
'a.b.a.c'.startswith('ab')
```




    False




```python
'a.b.a.c'.startswith('a.')
```




    True




```python
'a.b.a.c'.startswith('ab',2)
```




    False




```python
'a.b.a.c'.startswith('a.',4)
```




    True




```python
'a.b.a.c'.startswith('a',1,4)
```




    False


