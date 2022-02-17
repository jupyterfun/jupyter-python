## 列表推导式

列表推导式提供了一个更简单的创建列表的方法。常见的用法是把某种操作应用于序列或可迭代对象的每个元素上，然后使用其结果来创建列表，或者通过满足某些特定条件元素来创建子序列。

对比下列两种创建数值平方列表的方式：


```python
squares = []
for x in range(5):
    squares.append(x**2)

print(squares)
print(x) # 产生了一个变量 x 
```

    [0, 1, 4, 9, 16]
    4
    


```python
squares = [y**2 for y in range(5)]
print(squares)
print(y) # 没有多余变量 y
```

    [0, 1, 4, 9, 16]
    


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-3-c81791cbad54> in <module>
          1 squares = [y**2 for y in range(5)]
          2 print(squares)
    ----> 3 print(y) #
    

    NameError: name 'y' is not defined


我们发现，列表推导式简洁漂亮、易读，不会产生多余的变量而可能带来副作用。

## 列表推导式示例:


```python
 [(x, y) for x in [1,2] for y in [1,3] if x != y]
```




    [(1, 3), (2, 1), (2, 3)]



相当于：


```python
_list = []
for x in [1,2]:
    for y in [1,3]:
        if x != y:
            _list.append((x,y))
_list
```




    [(1, 3), (2, 1), (2, 3)]



列表推导式可以使用复杂的表达式和嵌套函数：


```python
from math import pi
[str(round(pi, i)) for i in range(1, 4)]
```




    ['3.1', '3.14', '3.142']



嵌套的列表推导式：


```python
matrix = [[1, 2, 3],
          [5, 6, 7]]
[[row[i] for row in matrix] for i in range(3)]
```




    [[1, 5], [2, 6], [3, 7]]



相当于：


```python
matrix = [[1, 2, 3],
          [5, 6, 7]]
_list = []
for i in range(3):
    lst = []
    for row in matrix:
        lst.append(row[i])
    _list.append(lst)
_list
```




    [[1, 5], [2, 6], [3, 7]]



判断语句在前的列表推导式：


```python
[True if i % 2 == 0 else False for i in [1,4,7,9]]
```




    [False, True, False, False]



相当于：


```python
_list = []
for i in [1,4,7,9]:
    if i % 2 == 0:
        _list.append(True)
    else:
        _list.append(False)
_list
```




    [False, True, False, False]


