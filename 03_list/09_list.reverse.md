## list.reverse 反转列表中元素

列表方法 list.reverse()，Python 官方文档描述如下：


```python
help(list.reverse)
```

    Help on method_descriptor:
    
    reverse(self, /)
        Reverse *IN PLACE*.
    
    

反转列表中的元素。


```python
_list = [1,2,3]
_list.reverse()
_list
```




    [3, 2, 1]



该方法是一个过程 (过程就是不返回有意义结果的函数；在 Python 中，过程的返回值为 None), 直接对原列表进行修改：


```python
_list = [1,2,3]
a = _list.reverse()
print(a)
```

    None
    
