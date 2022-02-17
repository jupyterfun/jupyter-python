## str.find 查找最小索引

字符串方法 str.find()，Python 官方文档描述如下：


```python
help(str.find)
```

    Help on method_descriptor:
    
    find(...)
        S.find(sub[, start[, end]]) -> int
        
        Return the lowest index in S where substring sub is found,
        such that sub is contained within S[start:end].  Optional
        arguments start and end are interpreted as in slice notation.
        
        Return -1 on failure.
    
    

返回子字符串 sub 在 s[start:end] 切片内被找到的最小索引。可选参数 start 与 end 会被解读为切片表示法。如果 sub 未被找到则返回 -1。

只给定 sub 一个参数的话，于是从第一个字符开始搜索到字符串结束；如果，随后给定了一个可选参数的话，那么它是 start，于是从 start 开始，搜索到字符串结束；如果 start 之后还有参数的话，那么它是 end；于是从 start 开始，搜索到 end - 1 结束（即不包含索引值为 end 的那个字符）。


```python
'pythonpython'.find('y')
```




    1




```python
'pythonpython'.find('pt')
```




    -1




```python
'pythonpython'.find('y',5)
```




    7




```python
'pythonpython'.find('y',5,7)
```




    -1


