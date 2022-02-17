## map 以给定函数转换元素

内置函数（类）map，Python 官方文档描述如下：


```python
help(map)
```

    Help on class map in module builtins:
    
    class map(object)
     |  map(func, *iterables) --> map object
     |  
     |  Make an iterator that computes the function using arguments from
     |  each of the iterables.  Stops when the shortest iterable is exhausted.
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
    
    

返回一个将函数 func 应用于 iterable 中每一项并输出其结果的迭代器。

如果传入了额外的 iterable 参数，func 必须接受相同个数的实参并被应用于从所有可迭代对象中并行获取的项。

当有多个可迭代对象时，最短的可迭代对象耗尽则整个迭代就将结束。


```python
type(map)
```




    type




```python
a = map(int, '1234')
a
```




    <map at 0x16048be3828>




```python
list(a)
```




    [1, 2, 3, 4]




```python
m = map(int,'abc',(16,16))
list(m)
```




    [10, 11]




```python
def f(x,y):
    d = {}
    d[x] = y
    return d

m = map(f,'abc',(1,2))
list(m)
```




    [{'a': 1}, {'b': 2}]


