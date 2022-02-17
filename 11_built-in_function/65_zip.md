## zip 重组可迭代对象

内置函数（类）zip，Python 官方文档描述如下：


```python
help(zip)
```

    Help on class zip in module builtins:
    
    class zip(object)
     |  zip(iter1 [,iter2 [...]]) --> zip object
     |  
     |  Return a zip object whose .__next__() method returns a tuple where
     |  the i-th element comes from the i-th iterable argument.  The .__next__()
     |  method continues until the shortest iterable in the argument sequence
     |  is exhausted and then it raises StopIteration.
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
    
    

创建一个聚合了来自每个可迭代对象中的元素的迭代器。

返回一个元组的迭代器，其中的第 i 个元组包含来自每个可迭代对象的第 i 个元素。

当所输入可迭代对象中最短的一个被耗尽时，迭代器将停止迭代。

当只有一个可迭代对象参数时，它将返回一个单元组的迭代器。

不带参数时，它将返回一个空迭代器。


```python
type(zip)
```




    type




```python
zip()
```




    <zip at 0x2ac600edac8>




```python
list(zip('123'))
```




    [('1',), ('2',), ('3',)]




```python
list(zip('123',{3,2,1}))
```




    [('1', 1), ('2', 2), ('3', 3)]




```python
list(zip([3,2,1],(1,2,3,4),'12'))
```




    [(3, 1, '1'), (2, 2, '2')]




```python
list(zip(*['abc','123']))
```




    [('a', '1'), ('b', '2'), ('c', '3')]


