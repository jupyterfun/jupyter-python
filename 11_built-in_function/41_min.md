## min() 求最小项

内置函数 min()，Python 官方文档描述如下：


```python
help(min)
```

    Help on built-in function min in module builtins:
    
    min(...)
        min(iterable, *[, default=obj, key=func]) -> value
        min(arg1, arg2, *args, *[, key=func]) -> value
        
        With a single iterable argument, return its smallest item. The
        default keyword-only argument specifies an object to return if
        the provided iterable is empty.
        With two or more arguments, return the smallest argument.
    
    

返回可迭代对象中最小的元素，或多个实参中最小的项。参数说明：
- 如果只提供了一个位置参数，它必须是可迭代对象（iterable），返回 iterable 中最小的元素，iterable 为空，返回 default。
- 如果提供了两个及以上的位置参数，则返回最小的位置参数。
- 如果有多个最小元素，则此函数将返回第一个找到的。
- 参数 key（可选）指定排序函数，将排序的项都经此函数计算，按计算值取最小的项。


```python
min('3142')
```




    '1'




```python
min([], default=0)
```




    0




```python
min(2,3,2,4)
```




    2




```python
min([2,1],[2,1,1])
```




    [2, 1]




```python
min(('a','ab','bcd'),key=len)
```




    'a'


