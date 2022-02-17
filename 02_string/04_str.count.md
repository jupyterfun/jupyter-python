## str.count 统计

字符串方法 str.count()，Python 官方文档描述如下：


```python
help(str.count)
```

    Help on method_descriptor:
    
    count(...)
        S.count(sub[, start[, end]]) -> int
        
        Return the number of non-overlapping occurrences of substring sub in
        string S[start:end].  Optional arguments start and end are
        interpreted as in slice notation.
    
    

返回回子字符串 sub 在 [start, end] 范围内非重叠出现的次数。可选参数 start 与 end 会被解读为切片表示法。

只给定 sub 一个参数的话，于是从第一个字符开始搜索到字符串结束；如果，随后给定了一个可选参数的话，那么它是 start，于是从 start 开始，搜索到字符串结束；如果 start 之后还有参数的话，那么它是 end；于是从 start 开始，搜索到 end - 1 结束（即不包含索引值为 end 的那个字符）。


```python
'python'.count('0')
```




    0




```python
'pyyython'.count('yy')
```




    1




```python
'pythonpythonn'.count('n',5)
```




    3




```python
'pythonpythonn'.count('n',5,7)
```




    1


