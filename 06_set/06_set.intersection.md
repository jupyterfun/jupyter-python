## set.intersection 交集

集合方法 set.intersection()，Python 官方文档描述如下：


```python
help(set.intersection)
```

    Help on method_descriptor:
    
    intersection(...)
        Return the intersection of two sets as a new set.
        
        (i.e. all elements that are in both sets.)
    
    

该方法接收任意的位置参数，返回一个所有集合中共有的元素组成的新集合。相当于 a & b & ... （a，b 是集合），但方法中的参数可以是可迭代对象。


```python
{1,2,3}.intersection({3,4},[1,5,3])
```




    {3}




```python
{1,2,3} & {3,4} & {1,5,3}
```




    {3}


