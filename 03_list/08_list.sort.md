## list.sort 对列表原地排序

列表方法 list.sort()，Python 官方文档描述如下：


```python
help(list.sort)
```

    Help on method_descriptor:
    
    sort(self, /, *, key=None, reverse=False)
        Sort the list in ascending order and return None.
        
        The sort is in-place (i.e. the list itself is modified) and stable (i.e. the
        order of two equal elements is maintained).
        
        If a key function is given, apply it once to each list item and sort them,
        ascending or descending, according to their function values.
        
        The reverse flag can be set to sort in descending order.
    
    

此方法会对列表进行原地排序，只使用 `<` 来进行各项间比较。异常不会被屏蔽——如果有任何比较操作失败，整个排序操作将失败（而列表可能会处于被部分修改的状态）。


```python
_list = [2,3,6,1,'5']
_list.sort()
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-2-87abda0b5baf> in <module>
          1 _list = [2,3,6,1,'5']
    ----> 2 _list.sort()
    

    TypeError: '<' not supported between instances of 'str' and 'int'



```python
_list
```




    [1, 2, 3, 6, '5']



sort() 接受两个仅限以关键字形式传入的参数 (仅限关键字参数):
- key 指定带有一个参数的函数，应用于列表中的每一个元素，按求值之后的大小，对原列表进行排序。默认值 None 表示直接对列表项排序。


```python
_list = [-3,2,-5,1,4]
_list.sort(key=abs)
_list
```




    [1, 2, -3, 4, -5]




```python
_list.sort()
_list
```




    [-5, -3, 1, 2, 4]



- reverse 为一个布尔值。如果设为 True，则每个列表元素将按反向顺序比较进行排序。


```python
_list = [-3,2,-5,1,4]
_list.sort(reverse=True)
_list
```




    [4, 2, 1, -3, -5]



当对较大的列表排序时，此方法会原地修改该序列以保证空间经济性。因此它并不会返回排序后的序列。

sort() 方法确保是稳定的——如果一个排序确保不会改变比较结果相等的元素的相对顺序就称其为稳定的。


```python
_list = [1,'1.0',2,'1']
_list.sort(key=float)
_list
```




    [1, '1.0', '1', 2]



该方法是一个过程 (过程就是不返回有意义结果的函数；在 Python 中，过程的返回值为 None), 直接对原列表进行修改：


```python
_list = [5,1,4]
a = _list.sort()
print(a)
```

    None
    
