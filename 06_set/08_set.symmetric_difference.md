## set.symmetric_difference 对称差

集合方法 set.symmetric_difference()，Python 官方文档描述如下：


```python
help(set.symmetric_difference)
```

    Help on method_descriptor:
    
    symmetric_difference(...)
        Return the symmetric difference of two sets as a new set.
        
        (i.e. all elements that are in exactly one of the sets.)
    
    

返回两个集合中非共同元素组成的新集合。相当于 a ^ b（a，b 是集合），但方法的参数可以是可迭代对象。


```python
{1,2,3}.symmetric_difference([2,3,4])
```




    {1, 4}




```python
{1,2,3} ^ {2,3,4}
```




    {1, 4}


