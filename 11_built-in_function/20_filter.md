## filter 真值元素筛选

内置函数（类）filter，Python 官方文档描述如下：


```python
help(filter)
```

    Help on class filter in module builtins:
    
    class filter(object)
     |  filter(function or None, iterable) --> filter object
     |  
     |  Return an iterator yielding those items of iterable for which function(item)
     |  is true. If function is None, return the items that are true.
     |  
     |  Methods defined here:
     |  
     |  __getattribute__(self, name, /)
     |      Return getattr(self, name).
     |  
     |  __iter__(self, /)
     |      Implement iter(self).
     |  
     |  __next__(self, /)
     |      Implement next(self).
     |  
     |  __reduce__(...)
     |      Return state information for pickling.
     |  
     |  ----------------------------------------------------------------------
     |  Static methods defined here:
     |  
     |  __new__(*args, **kwargs) from builtins.type
     |      Create and return a new object.  See help(type) for accurate signature.
    
    

返回可迭代对象（iterable）中那些传递给函数 function 计算之后，布尔值仍然为真的元素组成的迭代器。

如果 function 是 None，则会假设它是一个身份函数，即 iterable
中所有布尔值为假的元素会被移除。


```python
type(filter)
```




    type




```python
f = filter(None,[0,1,2,1])
list(f)
```




    [1, 2, 1]




```python
f = filter(lambda x: x-1, [0,1,2,1])
list(f)
```




    [0, 2]




```python
list(filter(None,'0120'))
```




    ['0', '1', '2', '0']




```python
list(filter(int,'0120'))
```




    ['1', '2']


