## set.issuperset 是超集吗？

集合方法 set.issuperset()，Python 官方文档描述如下：


```python
help(set.issuperset)
```

    Help on method_descriptor:
    
    issuperset(...)
        Report whether this set contains another set.
    
    

检查一个集合是否是另一个集合的超集。相当于 a >= b（a，b 是两个集合），但方法中的参数可以是可迭代对象。


```python
{1,2}.issuperset({True:'1',2:'2'})
```




    True




```python
{1,2,3} >= {True,2}
```




    True



对于真超集，使用 `>` 进行检查：


```python
{1,2,3} > {True,2}
```




    True




```python
{1,2} > {True,2}
```




    False


