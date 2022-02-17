## 空值 None

空值 None，就是空对象的值，此对象会由没有显式地设置返回值的函数返回。None 是个内置名称，空对象求值，什么也不会发生。


```python
None
```


```python
help(None)
```

    Help on NoneType object:
    
    class NoneType(object)
     |  Methods defined here:
     |  
     |  __bool__(self, /)
     |      self != 0
     |  
     |  __repr__(self, /)
     |      Return repr(self).
     |  
     |  ----------------------------------------------------------------------
     |  Static methods defined here:
     |  
     |  __new__(*args, **kwargs) from builtins.type
     |      Create and return a new object.  See help(type) for accurate signature.
    
    


```python
# 没有返回值的列表方法
a = [].append(1)
a
```


```python
# 将 a 打印出来，将打印内置名称 None
print(a)
```

    None
    
