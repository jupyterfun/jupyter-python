## setattr() 设置或新增属性

内置函数 setattr()，Python 官方文档描述如下：


```python
help(setattr)
```

    Help on built-in function setattr in module builtins:
    
    setattr(obj, name, value, /)
        Sets the named attribute on the given object to the specified value.
        
        setattr(x, 'y', v) is equivalent to ``x.y = v''
    
    

参数为一个对象、一个字符串和一个任意值。字符串指定一个现有属性或者新增属性。函数会将值赋给该属性，只要对象允许这种操作。


```python
class A:
    y = 1
x = A()
x.y
```




    1




```python
# 为实例 x 新增属性
setattr(x, 'y', 10)
x.y
```




    10




```python
A.y
```




    1




```python
# 修改类 A 的 y 属性
setattr(A, 'y', 100)
A.y
```




    100




```python
x.y
```




    10


