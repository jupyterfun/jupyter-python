## dict.values 值视图

字典方法 dict.values()，Python 官方文档描述如下：


```python
help(dict.values)
```

    Help on method_descriptor:
    
    values(...)
        D.values() -> an object providing a view on D's values
    
    

返回由字典的值组成的动态视图。字典的视图支持成员检测，可以被迭代。


```python
d = {'a':1, 'b':2}
d_view = d.values()
print(d_view)
d['c'] = 3 # 添加元素，视图也动态变化
print(d_view)
```

    dict_values([1, 2])
    dict_values([1, 2, 3])
    


```python
1 in d_view
```




    True




```python
[i for i in d_view]
```




    [1, 2, 3]


