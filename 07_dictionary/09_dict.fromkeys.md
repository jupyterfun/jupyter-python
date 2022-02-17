## dict.fromkeys 创建字典

字典的方法 fromkeys，Python 官方文档描述如下：


```python
help(dict.fromkeys)
```

    Help on built-in function fromkeys:
    
    fromkeys(iterable, value=None, /) method of builtins.type instance
        Create a new dictionary with keys from iterable and values set to value.
    
    

使用可迭代对象 iterable 中的元素作为字典的键，value 为值（默认是 None）创建字典。


```python
dict.fromkeys('123')
```




    {'1': None, '2': None, '3': None}




```python
dict.fromkeys([1,2,3], 0)
```




    {1: 0, 2: 0, 3: 0}



可迭代对象中不能包含不可哈希对象：


```python
dict.fromkeys([[1],2,3], 0)
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-6-470a0d0c77b4> in <module>
    ----> 1 dict.fromkeys([[1],2,3], 0)
    

    TypeError: unhashable type: 'list'

