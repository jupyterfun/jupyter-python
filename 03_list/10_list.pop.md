## list.pop 删除元素并返回

列表方法 list.pop()，Python 官方文档描述如下：


```python
help(list.pop)
```

    Help on method_descriptor:
    
    pop(self, index=-1, /)
        Remove and return item at index (default last).
        
        Raises IndexError if list is empty or index is out of range.
    
    

删除列表中给定位置的元素并返回它。如果没有给定位置，list.pop() 将会删除并返回列表中的最后一个元素。给定位置超出范围，抛出 IndexError 错误。


```python
_list = [1,2,3,4]
_list.pop()
```




    4




```python
_list
```




    [1, 2, 3]




```python
_list.pop(0)
```




    1




```python
_list
```




    [2, 3]




```python
_list.pop(5)
```


    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    <ipython-input-4-efa5a84417c8> in <module>
    ----> 1 _list.pop(5)
    

    IndexError: pop index out of range

