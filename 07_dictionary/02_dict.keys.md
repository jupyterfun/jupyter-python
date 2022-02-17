## dict.keys 键视图

字典方法 dict.keys()，Python 官方文档描述如下：


```python
help(dict.keys)
```

    Help on method_descriptor:
    
    keys(...)
        D.keys() -> a set-like object providing a view on D's keys
    
    

返回一个由字典的键组成的动态视图。字典的视图支持成员检测，可以被迭代。


```python
d = {'a':1, 'b':2}
d.keys()
```




    dict_keys(['a', 'b'])




```python
'a' in d.keys()
```




    True




```python
list(d.keys())
```




    ['a', 'b']




```python
d = {'a':1, 'b':2}
d_view = d.keys()
print(d_view)
d['c'] = 3 # 添加元素，视图也动态变化
print(d_view)
```

    dict_keys(['a', 'b'])
    dict_keys(['a', 'b', 'c'])
    
