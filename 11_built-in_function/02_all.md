## all() 所有元素布尔值为真？

内置函数 all()，Python 官方文档描述如下：


```python
help(all)
```

    Help on built-in function all in module builtins:
    
    all(iterable, /)
        Return True if bool(x) is True for all values x in the iterable.
        
        If the iterable is empty, return True.
    
    

如果可迭代对象（iterable）的所有元素均为真值（或可迭代对象为空）则返回 True 。


```python
all('0123') # 字符串 '0' 是真值
```




    True




```python
all([0,1,2,3])
```




    False




```python
all({})
```




    True




```python
all({1:[], 2:0 })
```




    True


