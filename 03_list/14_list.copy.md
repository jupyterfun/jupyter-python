## list.copy 列表的一个浅拷贝

列表方法 list.copy()，Python 官方文档描述如下：


```python
help(list.copy)
```

    Help on method_descriptor:
    
    copy(self, /)
        Return a shallow copy of the list.
    
    

返回列表的一个浅拷贝。相当于 a[:]（a 是一个列表）。浅拷贝得到新的列表，列表中有可变对象时，浅拷贝中的可变对象元素，是原列表中同一个对象的多次引用。


```python
list_1 = [[1],2,3]
list_2 = list_1.copy()
print(list_2)
id(list_1),id(list_2)
```

    [[1], 2, 3]
    




    (2622792783240, 2622792782728)




```python
# 同一个对象
id(list_1[0]), id(list_2[0])
```




    (2622792782792, 2622792782792)



改变其中一个都会跟着改变：


```python
list_1[0][:] = 'abc'
list_1, list_2
```




    ([['a', 'b', 'c'], 2, 3], [['a', 'b', 'c'], 2, 3])


