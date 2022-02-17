## list.remove 移除一个元素

列表方法 list.remove()，Python 官方文档描述如下：


```python
help(list.remove)
```

    Help on method_descriptor:
    
    remove(self, value, /)
        Remove first occurrence of value.
        
        Raises ValueError if the value is not present.
    
    

移除列表中第一个值为 value 的元素。如果没有这样的元素，则抛出 ValueError 异常。


```python
_list = [1,3,2,3]
_list.remove(3)
_list
```




    [1, 2, 3]




```python
_list.remove(4)
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-3-5747ddae04fe> in <module>
    ----> 1 _list.remove(4)
    

    ValueError: list.remove(x): x not in list


该方法是一个过程 (过程就是不返回有意义结果的函数；在 Python 中，过程的返回值为 None), 直接对原列表进行修改：


```python
_list = [1,3,2,3]
a = _list.remove(3)
print(a)
```

    None
    
