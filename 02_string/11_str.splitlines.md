## str.splitlines 按行拆分

字符串方法 str.splitlines()，Python 官方文档描述如下：


```python
help(str.splitlines)
```

    Help on method_descriptor:
    
    splitlines(self, /, keepends=False)
        Return a list of the lines in the string, breaking at line boundaries.
        
        Line breaks are not included in the resulting list unless keepends is given and
        true.
    
    

返回由原字符串中各行组成的列表，在行边界的位置拆分。结果列表中不包含行边界，除非给出了 keepends 且为真值。

此方法会以下列行边界进行拆分。特别地，行边界是 universal newlines 的一个超集。

- `\n` 换行
- `\r` 回车
- `\r\n` 回车 + 换行
- `\v` 或 `\x0b` 行制表符
- `\f` 或 `\x0c` 换表单
- `\x1c` 文件分隔符
- `\x1d` 组分隔符
- `\x1e` 记录分隔符
- `\x85` 下一行
- `\u2028` 行分隔符
- `\u2029` 段分隔符


```python
'ab c\n\nde fg\rkl\r\n'.splitlines()
```




    ['ab c', '', 'de fg', 'kl']




```python
'ab c\n\nde fg\rkl\r\n'.splitlines(keepends=True)
```




    ['ab c\n', '\n', 'de fg\r', 'kl\r\n']



分隔空字符串此方法将返回一个空列表；末尾的换行不会令结果中增加额外的空字符串:


```python
''.splitlines()
```




    []




```python
"One line\nTwo lines\n".splitlines()
```




    ['One line', 'Two lines']




```python
'One line\nTwo lines\n'.split('\n')
```




    ['One line', 'Two lines', '']


