## set.difference 差集

集合方法 set.difference()，Python 官方文档描述如下：


```python
help(set.difference)
```

    Help on method_descriptor:
    
    difference(...)
        Return the difference of two or more sets as a new set.
        
        (i.e. all elements that are in this set but not the others.)
    
    

该方法接收任意的位置参数，返回一个集合在其他所有集合中都不存在的元素组成的新集合。相当于 a - b - ... （a，b 是集合），但方法的参数可以是可迭代对象。


```python
{1,2,3,4}.difference((2,1,5),{6,2,4})
```




    {3}




```python
{1,2,3,4} - {2,1,5} - {6,2,4}
```




    {3}


