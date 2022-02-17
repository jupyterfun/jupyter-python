## set.pop 删除元素并返回

集合方法 set.pop()，Python 官方文档描述如下：


```python
help(set.pop)
```

    Help on method_descriptor:
    
    pop(...)
        Remove and return an arbitrary set element.
        Raises KeyError if the set is empty.
    
    

集合中删除任意一个元素，并返回它。如果集合为空，引发 KeyError。


```python
a = {1,2}
a.pop()
```




    1




```python
a
```




    {2}




```python
set().pop()
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    <ipython-input-6-db3bab0ab3b8> in <module>
    ----> 1 set().pop()
    

    KeyError: 'pop from an empty set'

