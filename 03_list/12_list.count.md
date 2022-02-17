## list.count 统计元素出现次数

列表方法 list.count()，Python 官方文档描述如下：


```python
help(list.count)
```

    Help on method_descriptor:
    
    count(self, value, /)
        Return number of occurrences of value.
    
    

返回元素 value 在列表中出现的次数，没有出现为 0。


```python
_list = [1,2,3,1]
_list.count(1), _list.count([1])
```




    (2, 0)


