## set.copy 浅拷贝

集合方法 set.copy()，Python 官方文档描述如下：


```python
help(set.copy)
```

    Help on method_descriptor:
    
    copy(...)
        Return a shallow copy of a set.
    
    

返回集合的一个浅拷贝。


```python
a = {1,2}
print(id(a),a)
b = a.copy()
id(b),b
```

    2091426558696 {1, 2}
    




    (2091426559368, {1, 2})


