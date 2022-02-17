## list.extend 加入可迭代对象中元素

列表方法 list.extend()，Python 官方文档描述如下：


```python
help(list.extend)
```

    Help on method_descriptor:
    
    extend(self, iterable, /)
        Extend list by appending elements from the iterable.
    
    

使用可迭代对象中的所有元素来扩展列表。相当于 a[len(a):] = iterable（a 是一个列表）。


```python
_list = [1,2]
_list.extend('abc')
_list
```




    [1, 2, 'a', 'b', 'c']




```python
_list.extend(range(2))
_list
```




    [1, 2, 'a', 'b', 'c', 0, 1]



该方法是一个过程 (过程就是不返回有意义结果的函数；在 Python 中，过程的返回值为 None), 直接对原列表进行修改：


```python
_list = [1,2]
a = _list.extend('abc')
print(a)
```

    None
    
