## set.union 并集

集合方法 set.union()，Python 官方文档描述如下：


```python
help(set.union)
```

    Help on method_descriptor:
    
    union(...)
        Return the union of sets as a new set.
        
        (i.e. all elements that are in either set.)
    
    

该方法接收任意的位置参数，返回一个所有集合的元素组成的新集合。相当于 a | b | ... （a，b 是集合），但方法中的参数可以是可迭代对象。


```python
{1}.union([2],(3,4))
```




    {1, 2, 3, 4}




```python
{1} | {2} | {3,4}
```




    {1, 2, 3, 4}


