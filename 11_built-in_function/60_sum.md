## sum() 数字求和或序列拼接

内置函数 sum()，Python 官方文档描述如下：


```python
help(sum)
```

    Help on built-in function sum in module builtins:
    
    sum(iterable, start=0, /)
        Return the sum of a 'start' value (default: 0) plus an iterable of numbers
        
        When the iterable is empty, return the start value.
        This function is intended specifically for use with numeric values and may
        reject non-numeric types.
    
    

通常对一个以数字为元素的可迭代对象求和并返回和。如果指定 start 参数，和需要加上 start。

start 不能为字符串，拼接字符串 sum() 不支持，更好更快的方式是 str.join() 方法。

sum() 还支持其他序列（列表和元组）。


```python
sum([1,2,3])
```




    6




```python
sum(range(4), 10)
```




    16




```python
sum([(1,2),(3,4)], (5,))
```




    (5, 1, 2, 3, 4)




```python
sum([[1,2],[3]],[0])
```




    [0, 1, 2, 3]


