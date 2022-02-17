## str.rindex 查找最大索引

字符串方法 str.rindex()，Python 官方文档描述如下：


```python
help(str.rindex)
```

    Help on method_descriptor:
    
    rindex(...)
        S.rindex(sub[, start[, end]]) -> int
        
        Return the highest index in S where substring sub is found,
        such that sub is contained within S[start:end].  Optional
        arguments start and end are interpreted as in slice notation.
        
        Raises ValueError when the substring is not found.
    
    

返回子字符串 sub 在字符串内被找到的最大（最右）索引，这样 sub 将包含在 s[start:end] 当中。可选参数 start 与 end 会被解读为切片表示法。如果未找到则返回 -1。类似于 rfind()，但在子字符串 sub 未找到时会引发 ValueError。

只给定 sub 一个参数的话，于是从第一个字符开始搜索到字符串结束；如果，随后给定了一个可选参数的话，那么它是 start，于是从 start 开始，搜索到字符串结束；如果 start 之后还有参数的话，那么它是 end；于是从 start 开始，搜索到 end - 1 结束（即不包含索引值为 end 的那个字符）。


```python
'python python'.rindex('on')
```




    11




```python
'python python'.rindex('on',1,7)
```




    4




```python
'python python'.rindex('on',7)
```




    11




```python
'python python'.rindex('no')
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-5-92aeb174dba9> in <module>
    ----> 1 'python python'.rindex('no')
    

    ValueError: substring not found

