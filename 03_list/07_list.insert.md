## list.insert 插入一个元素

列表方法 list.insert()，Python 官方文档描述如下：


```python
help(list.insert)
```

    Help on method_descriptor:
    
    insert(self, index, object, /)
        Insert object before index.
    
    

在给定的位置插入一个元素。第一个参数是要插入的元素的索引，所以 a.insert(0, x) 插入列表头部，a.insert(len(a), x) 等同于 a.append(x)（a 是一个列表）。


```python
_list = [1,2,3]
_list.insert(0,0)
_list
```




    [0, 1, 2, 3]




```python
_list.insert(len(_list),[4])
_list
```




    [0, 1, 2, 3, [4]]



该方法是一个过程 (过程就是不返回有意义结果的函数；在 Python 中，过程的返回值为 None), 直接对原列表进行修改：


```python
_list = [1,2,3]
a = _list.insert(0,0)
print(a)
```

    None
    
