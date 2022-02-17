## set.difference_update 差集更新

集合方法 set.difference_update()，Python 官方文档描述如下：


```python
help(set.difference_update)
```

    Help on method_descriptor:
    
    difference_update(...)
        Remove all elements of another set from this set.
    
    

该方法接收任意的位置参数，更新集合，移除在其他集合中也存在的元素。相当于 a -= b | ...（a，b 是集合），但方法的参数可以是可迭代对象。


```python
a = {1,2,3,4}
a.difference_update((1,3,5),[4,5])
a
```




    {2}




```python
a = {1,2,3,4}
a -= {1,3,5} | {4,5}
a
```




    {2}



该方法是一个过程，就地修改集合，返回值为 None。


```python
a = {1,2,3,4}
b = a.difference_update([4,5])
print(b)
```

    None
    
