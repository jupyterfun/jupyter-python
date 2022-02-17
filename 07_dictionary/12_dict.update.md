## dict.update 更新字典

字典方法 dict.update()，Python 官方文档描述如下：


```python
help(dict.update)
```

    Help on method_descriptor:
    
    update(...)
        D.update([E, ]**F) -> None.  Update D from dict/iterable E and F.
        If E is present and has a .keys() method, then does:  for k in E: D[k] = E[k]
        If E is present and lacks a .keys() method, then does:  for k, v in E: D[k] = v
        In either case, this is followed by: for k in F:  D[k] = F[k]
    
    

更新字典，键相同，则覆盖原有的值，不同，则增加 键值对 元素。有下列几种情况：
- 以字典更新字典：


```python
d = {'a':1, 'b':2}
d.update({'a':10, 'c':3})
d
```




    {'a': 10, 'b': 2, 'c': 3}



- 以可迭代对象更新字典：


```python
d = {'a':1, 'b':2}
d.update([('a',10),['c',3]])
d
```




    {'a': 10, 'b': 2, 'c': 3}



- 以关键字参数更新字典：


```python
d = {'a':1, 'b':2}
d.update(a=10, c=3)
d
```




    {'a': 10, 'b': 2, 'c': 3}


