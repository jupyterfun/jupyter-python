## dict.items 键值对视图

字典方法 dict.items()，Python 官方文档描述如下：


```python
help(dict.items)
```

    Help on method_descriptor:
    
    items(...)
        D.items() -> a set-like object providing a view on D's items
    
    

返回字典的 (键,值) 元组组成的动态视图。字典的视图支持成员检测，可以被迭代。


```python
d = {'a':1, 'b':2}
d_view = d.items()
print(d_view)
d['c'] = 3 # 添加元素，视图也动态变化
print(d_view)
```

    dict_items([('a', 1), ('b', 2)])
    dict_items([('a', 1), ('b', 2), ('c', 3)])
    


```python
('a', 1) in d_view
```




    True




```python
[k*j for k, j in d_view]
```




    ['a', 'bb', 'ccc']


