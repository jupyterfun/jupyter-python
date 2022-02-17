## set.discard 删除元素

集合方法 set.discard()，Python 官方文档描述如下：


```python
help(set.discard)
```

    Help on method_descriptor:
    
    discard(...)
        Remove an element from a set if it is a member.
        
        If the element is not a member, do nothing.
    
    

从集合中删除一个指定元素，元素不存在没有任何影响。


```python
a = {1,2}
a.discard(1)
a
```




    {2}




```python
a = {1,2}
a.discard(3)
a
```




    {1, 2}



该方法是一个过程，就地修改集合，返回值为 None。


```python
a = {1,2}
b = a.discard(1)
print(b)
```

    None
    
