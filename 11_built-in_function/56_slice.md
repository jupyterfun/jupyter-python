## slice 创建切片对象

内置函数（类）slice，Python 官方文档描述如下：


```python
help(slice)
```

    Help on class slice in module builtins:
    
    class slice(object)
     |  slice(stop)
     |  slice(start, stop[, step])
     |  
     |  Create a slice object.  This is used for extended slicing (e.g. a[0:10:2]).
     |  
     |  Methods defined here:
     |  
     |  __eq__(self, value, /)
     |      Return self==value.
     |  
     |  __ge__(self, value, /)
     |      Return self>=value.
     |  
     |  __getattribute__(self, name, /)
     |      Return getattr(self, name).
     |  
     |  __gt__(self, value, /)
     |      Return self>value.
     |  
     |  __le__(self, value, /)
     |      Return self<=value.
     |  
     |  __lt__(self, value, /)
     |      Return self<value.
     |  
     |  __ne__(self, value, /)
     |      Return self!=value.
     |  
     |  __reduce__(...)
     |      Return state information for pickling.
     |  
     |  __repr__(self, /)
     |      Return repr(self).
     |  
     |  indices(...)
     |      S.indices(len) -> (start, stop, stride)
     |      
     |      Assuming a sequence of length len, calculate the start and stop
     |      indices, and the stride length of the extended slice described by
     |      S. Out of bounds indices are clipped in a manner consistent with the
     |      handling of normal slices.
     |  
     |  ----------------------------------------------------------------------
     |  Static methods defined here:
     |  
     |  __new__(*args, **kwargs) from builtins.type
     |      Create and return a new object.  See help(type) for accurate signature.
     |  
     |  ----------------------------------------------------------------------
     |  Data descriptors defined here:
     |  
     |  start
     |  
     |  step
     |  
     |  stop
     |  
     |  ----------------------------------------------------------------------
     |  Data and other attributes defined here:
     |  
     |  __hash__ = None
    
    

返回一个表示由 range(start, stop, step) 指定索引集的 slice 对象。其中 start 和 step 参数默认为 None。

切片对象具有仅会返回对应参数值（或其默认值）的只读数据属性 start, stop 和 step。它们没有其他的显式功能。


```python
type(slice)
```




    type




```python
s = slice(3)
s
```




    slice(None, 3, None)




```python
a = list(range(5))
a[s]
```




    [0, 1, 2]




```python
slice(2,8,2)
```




    slice(2, 8, 2)




```python
list(range(10)[slice(2,8,2)])
```




    [2, 4, 6]


