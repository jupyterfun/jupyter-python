## dict.get 获取某个键的值

字典方法 dict.get()，Python 官方文档描述如下：


```python
help(dict.get)
```

    Help on method_descriptor:
    
    get(self, key, default=None, /)
        Return the value for key if key is in the dictionary, else default.
    
    

获取字典的项目，如果 key 存在于字典中则返回 key 的值，否则返回 default 指定的值，默认为 None。


```python
d = {'a':1, 'b':2}
d.get('a')
```




    1




```python
print(d.get('c'))
```

    None
    


```python
d.get('c', 3)
```




    3


