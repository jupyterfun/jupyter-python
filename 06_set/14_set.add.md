## set.add 添加元素

集合方法 set.add()，Python 官方文档描述如下：


```python
help(set.add)
```

    Help on method_descriptor:
    
    add(...)
        Add an element to a set.
        
        This has no effect if the element is already present.
    
    

集合中增加一个元素，如果元素已经存在，没有任何影响。


```python
a = {1,2}
a.add(3)
a
```




    {1, 2, 3}




```python
a = {1,2}
a.add(1)
a
```




    {1, 2}



该方法是一个过程，就地修改集合，返回值为 None。


```python
a = {1,2}
b = a.add(3)
print(b)
```

    None
    
