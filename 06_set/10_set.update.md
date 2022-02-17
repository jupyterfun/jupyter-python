## set.update 合并更新

集合方法 set.update()，Python 官方文档描述如下：


```python
help(set.update)
```

    Help on method_descriptor:
    
    update(...)
        Update a set with the union of itself and others.
    
    

该方法接收任意的位置参数，将其他集合的元素合并到一个集合中。相当于 a |= b | ... （a，b 是集合），但方法的参数可以是可迭代对象。


```python
a = {1,2}
a.update([3],(4,5))
a
```




    {1, 2, 3, 4, 5}




```python
a = {1,2}
a |= {3} | {4,5}
a
```




    {1, 2, 3, 4, 5}



该方法是一个过程，就地修改集合，返回值为 None。


```python
a = {1,2}
b = a.update([3],(4,5))
print(b)
```

    None
    
