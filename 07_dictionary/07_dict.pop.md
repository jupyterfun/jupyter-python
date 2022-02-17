## dict.pop 删除元素并返回值

字典方法 dict.pop()，Python 官方文档描述如下：


```python
help(dict.pop)
```

    Help on method_descriptor:
    
    pop(...)
        D.pop(k[,d]) -> v, remove specified key and return the corresponding value.
        If key is not found, d is returned if given, otherwise KeyError is raised
    
    

如果字典的键 k 存在，则移除 k 对应的 键值对，并返回 值；

如果 k 不存在，但指定了可选参数 d，则返回 d；

如果 k 不存在且未指定 d，则引发 KeyError。


```python
d = {'a':1, 'b':2}
d.pop('a')
```




    1




```python
d = {'a':1, 'b':2}
d.pop('c', 3)
```




    3




```python
d = {'a':1, 'b':2}
d.pop('c')
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    <ipython-input-4-1e5ab2c0b86c> in <module>
          1 d = {'a':1, 'b':2}
    ----> 2 d.pop('c')
    

    KeyError: 'c'

