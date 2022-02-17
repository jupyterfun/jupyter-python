## str.zfill 填充 0 

字符串方法 str.zfill()，Python 官方文档描述如下：


```python
help(str.zfill)
```

    Help on method_descriptor:
    
    zfill(self, width, /)
        Pad a numeric string with zeros on the left, to fill a field of the given width.
        
        The string is never truncated.
    
    

返回原字符串的副本，在左边填充 ASCII '0' 数码使其长度变为 width。正负值前缀 ('+'/'-') 的处理方式是在正负符号 之后填充而非在之前。如果 width 小于等于 len(str) 则返回原字符串的副本。


```python
"42a".zfill(5)
```




    '0042a'




```python
"-42".zfill(5)
```




    '-0042'




```python
"-42".zfill(1)
```




    '-42'


