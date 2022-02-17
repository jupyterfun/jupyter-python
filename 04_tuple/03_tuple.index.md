## tuple.index 查找元素索引

元组方法 tuple.index()，Python 官方文档描述如下：


```python
help(tuple.index)
```

    Help on method_descriptor:
    
    index(self, value, start=0, stop=9223372036854775807, /)
        Return first index of value.
        
        Raises ValueError if the value is not present.
    
    

返回列表中第一个值为 value 的元素从零开始的索引。如果没有这样的元素将会抛出 ValueError 异常。

可选参数 start 和 stop 是切片符号，用于将搜索限制为元组的特定子序列。返回的是相对于整个序列开始计算的索引，而不是相对于 start 参数。


```python
(1,2,3,4,1).index(1)
```




    0




```python
(1,2,3,4,1).index(1,1)
```




    4




```python
(1,2,3,4,1).index(1,1,3)
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-4-c6a812394eea> in <module>
    ----> 1 (1,2,3,4,1).index(1,1,3)
    

    ValueError: tuple.index(x): x not in tuple

