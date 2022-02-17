## str.endswith 指定字符串结尾？

字符串方法 str.endswith()，Python 官方文档描述如下：


```python
help(str.endswith)
```

    Help on method_descriptor:
    
    endswith(...)
        S.endswith(suffix[, start[, end]]) -> bool
        
        Return True if S ends with the specified suffix, False otherwise.
        With optional start, test S beginning at that position.
        With optional end, stop comparing S at that position.
        suffix can also be a tuple of strings to try.
    
    

如果字符串以指定的 suffix 结束返回 True，否则返回 False。suffix 也可以为由多个供查找的后缀构成的元组。如果有可选项 start，将从所指定位置开始检查。如果有可选项 end，将在所指定位置之前停止比较。


```python
'python.exe'.endswith('.exe')
```




    True




```python
'python.exe'.endswith(('.exe','.txt'), 5)
```




    True




```python
'python.exe'.endswith(('.py','.txt'), 5)
```




    False




```python
'python.exe'.endswith(('.exe','.txt'), 5,9)
```




    False


