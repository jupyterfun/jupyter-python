## dict.popitem 删除元素并返回键值对

字典方法 dict.popitem()，Python 官方文档描述如下：


```python
help(dict.popitem)
```

    Help on method_descriptor:
    
    popitem(self, /)
        Remove and return a (key, value) pair as a 2-tuple.
        
        Pairs are returned in LIFO (last-in, first-out) order.
        Raises KeyError if the dict is empty.
    
    

按 后进先出 的原则，删除字典的元素，并以 (key, value) 元组返回。如果字典为空，则引发 KeyError。


```python
d = {2:2,1:1}
d.popitem()
```




    (1, 1)




```python
d = {}
d[1] = 1
d[3] = 3
d[2] = 2
d[3] = 30 # 更新并不改变元素插入顺序
d.popitem(),d.popitem(),d.popitem()
```




    ((2, 2), (3, 30), (1, 1))




```python
d = {}
d.popitem()
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    <ipython-input-13-3d5a99fd0340> in <module>
          1 d = {}
    ----> 2 d.popitem()
    

    KeyError: 'popitem(): dictionary is empty'

