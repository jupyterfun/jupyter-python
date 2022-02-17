## enumerate 枚举

内置函数（类）enumerate，Python 官方文档描述如下：


```python
help(enumerate)
```

    Help on class enumerate in module builtins:
    
    class enumerate(object)
     |  enumerate(iterable, start=0)
     |  
     |  Return an enumerate object.
     |  
     |    iterable
     |      an object supporting iteration
     |  
     |  The enumerate object yields pairs containing a count (from start, which
     |  defaults to zero) and a value yielded by the iterable argument.
     |  
     |  enumerate is useful for obtaining an indexed list:
     |      (0, seq[0]), (1, seq[1]), (2, seq[2]), ...
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
    
    

返回一个可迭代对象（iterable）的枚举对象。枚举对象是一个迭代器，迭代出来是一个个元组，里面包含一个计数值（从 start 开始，默认为 0）和通过迭代 iterable 获得的值。


```python
type(enumerate)
```




    type




```python
e = enumerate({'a':1,'b':2,'c':3})
e
```




    <enumerate at 0x200ccb71240>




```python
next(e)
```




    (0, 'a')




```python
for i in e:
    print(i)
```

    (1, 'b')
    (2, 'c')
    


```python
e = enumerate('abc', 1)
list(e)
```




    [(1, 'a'), (2, 'b'), (3, 'c')]


