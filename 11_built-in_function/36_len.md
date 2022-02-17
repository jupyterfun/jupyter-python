## len() 返回元素个数

内置函数 len()，Python 官方文档描述如下：


```python
help(len)
```

    Help on built-in function len in module builtins:
    
    len(obj, /)
        Return the number of items in a container.
    
    

返回对象的长度（元素个数）。实参可以是序列（如 str、bytes、tuple、list 或 range 等的实例），集合（set 或 frozenset 的实例），或字典（dict 的实例）等。


```python
len('123')
```




    3




```python
len('嗨')
```




    1




```python
len('嗨'.encode())
```




    3




```python
len([1,2,3])
```




    3




```python
len({'a':1,'b':2})
```




    2


