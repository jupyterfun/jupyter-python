## sorted() 返回排序列表

内置函数 sorted()，Python 官方文档描述如下：


```python
help(sorted)
```

    Help on built-in function sorted in module builtins:
    
    sorted(iterable, /, *, key=None, reverse=False)
        Return a new list containing all items from the iterable in ascending order.
        
        A custom key function can be supplied to customize the sort order, and the
        reverse flag can be set to request the result in descending order.
    
    

根据 iterable 中的项返回一个新的已排序列表。

具有两个可选参数，它们都必须指定为关键字参数。

key 指定带有单个参数的函数，应用于 iterable 中的每个元素，将计算结果用来对原 iterable 排序。默认值为 None (直接比较)。

reverse 为一个布尔值。如果设为 True，则每个列表元素将按反向顺序比较进行排序。

sorted() 排序确保是稳定的。如果一个排序确保不会改变比较结果相等的元素的相对顺序就称其为稳定的 --- 这有利于进行多重排序。


```python
sorted({'b':1,'a':3,'c':2})
```




    ['a', 'b', 'c']




```python
d = [{'age':18},{'age':30},{'age':26}]
sorted(d,key=lambda x:x['age'])
```




    [{'age': 18}, {'age': 26}, {'age': 30}]




```python
sorted([1.5,'2.0','1.5',3.14], key=float)
```




    [1.5, '1.5', '2.0', 3.14]




```python
sorted('3123', reverse=True)
```




    ['3', '3', '2', '1']


