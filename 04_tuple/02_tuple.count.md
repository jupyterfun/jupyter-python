## tuple.count 统计元素出现次数

元组方法 tuple.count()，Python 官方文档描述如下：


```python
help(tuple.count)
```

    Help on method_descriptor:
    
    count(self, value, /)
        Return number of occurrences of value.
    
    

返回值为 value 的元素在元组中的出现次数。


```python
(1,2,1,3).count(1)
```




    2




```python
(1,2,1,3).count(4)
```




    0


