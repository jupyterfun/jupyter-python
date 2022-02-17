## set.clear 清空集合元素

集合方法 set.clear()，Python 官方文档描述如下：


```python
help(set.clear)
```

    Help on method_descriptor:
    
    clear(...)
        Remove all elements from this set.
    
    

清空集合所有元素。


```python
a = {1,2}
a.clear()
a
```




    set()



该方法是一个过程，就地修改集合，返回值为 None。


```python
a = {1,2}
b = a.clear()
print(b)
```

    None
    
