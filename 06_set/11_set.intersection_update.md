## set.intersection_update 交集更新

集合方法 set.intersection_update()，Python 官方文档描述如下：


```python
help(set.intersection_update)
```

    Help on method_descriptor:
    
    intersection_update(...)
        Update a set with the intersection of itself and another.
    
    

该方法接收任意的位置参数，更新集合，只保留在其他所有集合中都存在的元素。相当于 a &= b & ...（a，b 是集合），但方法的参数可以是可迭代对象。


```python
a = {1,2,3,4}
a.intersection_update((1,2,5),{1,3,5})
a
```




    {1}




```python
a = {1,2,3,4}
a &= {1,2,5} & {1,3,5}
a
```




    {1}



该方法是一个过程，就地修改集合，返回值为 None。


```python
a = {1,2,3,4}
b = a.intersection_update()
print(b)
```

    None
    
