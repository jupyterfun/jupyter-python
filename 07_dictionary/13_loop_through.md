## 字典遍历

字典是可迭代对象，可以遍历字典的元素。由于字典元素是 键值对，遍历比较特殊。

如果未指定遍历对象，默认遍历字典的键。很多函数将字典作为可迭代对象处理时，也是如此。


```python
d = {'a':1, 'c':3, 'b':2}
for k in d:
    print(k)
```

    a
    c
    b
    


```python
list(d)
```




    ['a', 'c', 'b']




```python
sorted(d)
```




    ['a', 'b', 'c']




```python
max(d)
```




    'c'



可以利用字典的视图指定遍历字典的键（默认就是遍历键，可以省略），值 或是 键值对。


```python
d = {'a':1, 'c':3, 'b':2}
for k in d.keys(): # 可以不用视图
    print(k)
```

    a
    c
    b
    


```python
d = {'a':1, 'c':3, 'b':2}
for k in d.values(): 
    print(k)
```

    1
    3
    2
    


```python
d = {'a':1, 'c':3, 'b':2}
for k,v in d.items(): 
    print(k,v)
```

    a 1
    c 3
    b 2
    


```python
# 按值排序后再遍历
d = {'a':1, 'c':3, 'b':2}
for k,v in sorted(d.items(),key=lambda x:x[1]): 
    print(k,v)
```

    a 1
    b 2
    c 3
    
