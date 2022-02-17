## dict.clear 清空字典元素

字典方法 dict.clear()，Python 官方文档描述如下：


```python
help(dict.clear)
```

    Help on method_descriptor:
    
    clear(...)
        D.clear() -> None.  Remove all items from D.
    
    

清空字典元素。


```python
d = {'a':1, 'b':2}
d.clear()
d
```




    {}



该方法是一个过程，返回值为 None。


```python
d = {'a':1, 'b':2}
print(d.clear())
```

    None
    
