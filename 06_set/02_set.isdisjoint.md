## set.isdisjoint 交集为空吗？

集合方法 set.isdisjoint()，Python 官方文档描述如下：


```python
help(set.isdisjoint)
```

    Help on method_descriptor:
    
    isdisjoint(...)
        Return True if two sets have a null intersection.
    
    

两个集合的交集为空，则返回 True。方法中的参数可以是可迭代对象。


```python
{1,2}.isdisjoint([1,2])
```




    False




```python
{1,2}.isdisjoint([3,4])
```




    True




```python
{1,2}.isdisjoint('12') # 参数是字符串而非数字
```




    True


