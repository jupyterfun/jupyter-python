## set.remove 删除元素

集合方法 set.remove()，Python 官方文档描述如下：


```python
help(set.remove)
```

    Help on method_descriptor:
    
    remove(...)
        Remove an element from a set; it must be a member.
        
        If the element is not a member, raise a KeyError.
    
    

删除一个指定元素，删除元素不存在则引发 KeyError。


```python
a = {1,2}
a.remove(1)
a
```




    {2}




```python
a = {1,2}
a.remove(3)
a
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    <ipython-input-3-d0f57d460301> in <module>
          1 a = {1,2}
    ----> 2 a.remove(3)
          3 a
    

    KeyError: 3


该方法是一个过程，就地修改集合，返回值为 None。


```python
a = {1,2}
b = a.remove(1)
print(b)
```

    None
    
