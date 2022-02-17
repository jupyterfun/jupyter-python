## iter() 转迭代器

内置函数 iter()，Python 官方文档描述如下：


```python
help(iter)
```

    Help on built-in function iter in module builtins:
    
    iter(...)
        iter(iterable) -> iterator
        iter(callable, sentinel) -> iterator
        
        Get an iterator from an object.  In the first form, the argument must
        supply its own iterator, or be a sequence.
        In the second form, the callable is called until it returns the sentinel.
    
    

将一个可迭代对象（iterable）或可调用对象（callable）转换为一个迭代器。

当参数是可调用对象时，需要提供参数 sentinel，生成的迭代器，每次
迭代时都会不带实参地调用 callable，返回 sentinel 时则触
发 StopIteration。


```python
a = iter('abcd')
a
```




    <str_iterator at 0x1c7eea4f910>




```python
next(a),next(a),next(a),next(a)
```




    ('a', 'b', 'c', 'd')




```python
a = iter(int, 1)
for i in range(3):
    print(next(a))
```

    0
    0
    0
    


```python
a = iter(int, 0)
next(a)
```


    ---------------------------------------------------------------------------

    StopIteration                             Traceback (most recent call last)

    <ipython-input-21-694e44f6d78c> in <module>
          1 a = iter(int, 0)
    ----> 2 next(a)
    

    StopIteration: 

