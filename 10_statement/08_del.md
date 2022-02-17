## del 语句

del 语句用来删除名称的绑定，删除对象的属性引用 或 删除可抽取、切片的可变容器的元素。

删除名称绑定：


```python
# 将值 (1,2) 绑定到名称 a, b, c
a = b = c = (1,2)
# 删除名称 b, c
del b,c
a
```




    (1, 2)




```python
b # 名称 b 已被删除
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-27-9185c0ba25e7> in <module>
    ----> 1 b # 名称 b 已被删除
    

    NameError: name 'b' is not defined



```python
class A:
    x = y = 1
A.x, A.y
```




    (1, 1)




```python
del A.y
print(A.x)
A.y # 属性名称 y 已被删除，不可引用值 1
```

    1
    


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-29-8ed1b3e470b1> in <module>
          1 del A.y
          2 print(A.x)
    ----> 3 A.y # 属性名称 y 已被删除，不可引用值 1
    

    AttributeError: type object 'A' has no attribute 'y'



```python
# 删除字典元素
d = {'a':1,'b':2}
del d['a'] # 删除键为 'a' 的元素
print(d)
d['a']
```

    {'b': 2}
    


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    <ipython-input-30-5d91a843f82e> in <module>
          3 del d['a'] # 删除键为 'a' 的元素
          4 print(d)
    ----> 5 d['a']
    

    KeyError: 'a'



```python
# 删除列表切片
_list = [1,2,3,4]
del _list[::2]
_list
```




    [2, 4]




```python
# 删除列表切片
_list = [1,2,3,4]
del _list[:] # 相当于 _list[:] = []
_list
```




    []


