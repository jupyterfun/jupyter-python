## list.index 查找最小索引

列表方法 list.index()，Python 官方文档描述如下：


```python
help(list.index)
```

    Help on method_descriptor:
    
    index(self, value, start=0, stop=9223372036854775807, /)
        Return first index of value.
        
        Raises ValueError if the value is not present.
    
    

返回列表中第一个值为 value 的元素从零开始的索引。如果没有这样的元素将会抛出 ValueError 异常。

可选参数 start 和 stop 是切片符号，用于将搜索限制为列表的特定子序列。返回的是相对于整个序列开始计算的索引，而不是相对于 start 参数。


```python
_list = [1,2,3,4,3]
_list.index(3)
```




    2




```python
_list.index(3,1,4)
```




    2




```python
_list.index(3,4,10)
```




    4




```python
_list.index(3,5,10)
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-6-3e258cbffc85> in <module>
    ----> 1 _list.index(3,5,10)
    

    ValueError: 3 is not in list

