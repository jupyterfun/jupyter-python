## max() 求最大项

内置函数 max()，Python 官方文档描述如下：


```python
help(max)
```

    Help on built-in function max in module builtins:
    
    max(...)
        max(iterable, *[, default=obj, key=func]) -> value
        max(arg1, arg2, *args, *[, key=func]) -> value
        
        With a single iterable argument, return its biggest item. The
        default keyword-only argument specifies an object to return if
        the provided iterable is empty.
        With two or more arguments, return the largest argument.
    
    

返回可迭代对象中最大的元素，或多个实参中最大的项。参数说明：
- 如果只提供了一个位置参数，它必须是可迭代对象（iterable），返回 iterable 中最大的元素，iterable 为空，返回 default。
- 如果提供了两个及以上的位置参数，则返回最大的位置参数。
- 如果有多个最大元素，则此函数将返回第一个找到的。
- 参数 key（可选）指定排序函数，将排序的项都经此函数计算，按计算值取最大的项。


```python
max('3142')
```




    '4'




```python
max([], default=0)
```




    0




```python
max(2,4,3,4)
```




    4




```python
max([2,1],[2,1,1])
```




    [2, 1, 1]




```python
max(('a','ab','bcd'),key=len)
```




    'bcd'


