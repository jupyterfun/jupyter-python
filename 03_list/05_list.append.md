## list.append 添加一个元素

列表方法 list.append()，Python 官方文档描述如下：


```python
help(list.append)
```

    Help on method_descriptor:
    
    append(self, object, /)
        Append object to the end of the list.
    
    

在列表的末尾添加**一个**元素。相当于 a[len(a):] = [x]（a 是一个列表）。添加的元素可以是任何对象。


```python
_list = [1,2]
_list.append('abc')
_list.append(list.append)
_list
```




    [1, 2, 'abc', <method 'append' of 'list' objects>]



该方法是一个过程 (过程就是不返回有意义结果的函数；在 Python 中，过程的返回值为 None), 直接对原列表进行修改：


```python
_list = []
a = _list.append('')
print(a)
```

    None
    
