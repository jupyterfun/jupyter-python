## reversed 序列逆置

内置函数（类）reversed，Python 官方文档描述如下：


```python
help(reversed)
```

    Help on class reversed in module builtins:
    
    class reversed(object)
     |  reversed(sequence, /)
     |  
     |  Return a reverse iterator over the values of the given sequence.
     |  
     |  Methods defined here:
     |  
     |  __getattribute__(self, name, /)
     |      Return getattr(self, name).
     |  
     |  __iter__(self, /)
     |      Implement iter(self).
     |  
     |  __length_hint__(...)
     |      Private method returning an estimate of len(list(it)).
     |  
     |  __next__(self, /)
     |      Implement next(self).
     |  
     |  __reduce__(...)
     |      Return state information for pickling.
     |  
     |  __setstate__(...)
     |      Set state information for unpickling.
     |  
     |  ----------------------------------------------------------------------
     |  Static methods defined here:
     |  
     |  __new__(*args, **kwargs) from builtins.type
     |      Create and return a new object.  See help(type) for accurate signature.
    
    

返回给定的序列逆置之后的迭代器。


```python
type(reversed)
```




    type




```python
reversed('1234')
```




    <reversed at 0x14b684fe460>




```python
list(reversed('1234'))
```




    ['4', '3', '2', '1']



因为字典顺序会确保为插入顺序，字典和字典视图都是可逆的。3.8 新版可以返回一个逆序获取字典键的迭代器。 


```python
d = reversed({'a':1,'b':2,'c':3})
list(d)
```




    ['c', 'b', 'a']


