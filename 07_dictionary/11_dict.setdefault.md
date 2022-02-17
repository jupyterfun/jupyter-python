## dict.setdefault 获取或插入元素

字典方法 dict.setdefault()，Python 官方文档描述如下：


```python
help(dict.setdefault)
```

    Help on method_descriptor:
    
    setdefault(self, key, default=None, /)
        Insert key with a value of default if key is not in the dictionary.
        
        Return the value for key if key is in the dictionary, else default.
    
    

如果字典存在键 key，则返回它的值；如果 key 不存在，则插入 key，以 default（默认 None）作为它的值，并返回。


```python
d = {'a':1, 'b':2}
d.setdefault('a')
```




    1




```python
d.setdefault('c', 3)
```




    3




```python
d
```




    {'a': 1, 'b': 2, 'c': 3}




```python
d.setdefault('c', 4) # 如果存在，并不会再次设置
```




    3




```python
d
```




    {'a': 1, 'b': 2, 'c': 3}


