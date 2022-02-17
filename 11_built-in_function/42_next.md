## next() 返回迭代器下一个元素

内置函数 next()，Python 官方文档描述如下：


```python
help(next)
```

    Help on built-in function next in module builtins:
    
    next(...)
        next(iterator[, default])
        
        Return the next item from the iterator. If default is given and the iterator
        is exhausted, it is returned instead of raising StopIteration.
    
    

返回迭代器（iterator）的下一个元素。如果迭代器耗尽，则返回给定的 default，如果没有默认值则触发 StopIteration。


```python
i = iter('123')
next(i,'迭代结束')
```




    '1'




```python
next(i,'迭代结束')
```




    '2'




```python
next(i,'迭代结束')
```




    '3'




```python
next(i,'迭代结束')
```




    '迭代结束'




```python
next(i,'迭代结束')
```




    '迭代结束'


