## list.clear 删除所有元素

列表方法 list.clear()，Python 官方文档描述如下：


```python
help(list.clear)
```

    Help on method_descriptor:
    
    clear(self, /)
        Remove all items from list.
    
    

删除列表中所有的元素。相当于 del a[:]（a 是列表）。


```python
_list = [1,2,3]
_list.clear()
_list
```




    []



del a[:] 是删除列表 a 中的所有元素，和 a 的浅拷贝无关：


```python
a = [1,2,3]
b = a[:]
del a[:]
a, b
```




    ([], [1, 2, 3])



该方法是一个过程 (过程就是不返回有意义结果的函数；在 Python 中，过程的返回值为 None), 直接对原列表进行修改：


```python
_list = [1,2,3]
a = _list.clear()
print(a)
```

    None
    
