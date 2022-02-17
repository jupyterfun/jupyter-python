## set.issubset 是子集吗？

集合方法 set.issubset()，Python 官方文档描述如下：


```python
help(set.issubset)
```

    Help on method_descriptor:
    
    issubset(...)
        Report whether another set contains this set.
    
    

检查一个集合中的元素，是否都在另一个集合中。相当于 a <= b（a，b 是两个集合），但方法中的参数可以是可迭代对象。


```python
{1,2}.issubset([1,2,3])
```




    True




```python
{1,2} <= {1,2,3}
```




    True




```python
{1,2}.issubset((1,1,2))
```




    True



该方法检查是否是子集，而对于真子集，可以使用 `<` 进行检查：


```python
{1,2} < {1,1,2}
```




    False




```python
{1,2} < {1,2,3}
```




    True


