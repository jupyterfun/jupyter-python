## dict.copy 浅拷贝

字典方法 dict.copy()，Python 官方文档描述如下：


```python
help(dict.copy)
```

    Help on method_descriptor:
    
    copy(...)
        D.copy() -> a shallow copy of D
    
    

返回字典的一个浅拷贝。字典是可变对象，浅拷贝将创建一个新字典，但如果字典中某个 键值对 的值是可变对象，则是同一个对象的多次引用。


```python
d = {'a':[1,2], 'b':3}
print(id(d), d)
d1 = d.copy()
print(id(d1), d1)
```

    2276967660712 {'a': [1, 2], 'b': 3}
    2276967660784 {'a': [1, 2], 'b': 3}
    


```python
# 同一个对象的多次引用
id(d['a']), id(d1['a'])
```




    (2276966678024, 2276966678024)




```python
# 改变一个都会改变
d['a'].extend('34')
print(d)
print(d1)
```

    {'a': [1, 2, '3', '4'], 'b': 3}
    {'a': [1, 2, '3', '4'], 'b': 3}
    
