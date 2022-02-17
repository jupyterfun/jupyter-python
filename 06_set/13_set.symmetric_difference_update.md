## set ^= other 对称差集更新

集合的对称差集更新操作，相当于集合方法 set.symmetric_difference_update，其文档描述如下：


```python
help(set.symmetric_difference_update)
```

    Help on method_descriptor:
    
    symmetric_difference_update(...)
        Update a set with the symmetric difference of itself and another.
    
    

更新集合，只保留两个集合中非共同部分。


```python
a = {1,2,3}
a.symmetric_difference_update([2,3,4])
a
```




    {1, 4}




```python
a = {1,2,3}
a ^= {2,3,4}
a
```




    {1, 4}



该方法是一个过程，就地修改集合，返回值为 None。


```python
a = {1,2,3}
b = a.symmetric_difference_update([2,3,4])
print(b)
```

    None
    
