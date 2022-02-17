## 表达式语句

语句分为简单语句和复合语句，简单语句由一个单独的逻辑行构成。多条简单语句可以存在于同一行内并以分号分隔。表达式语句属于简单语句。

表达式语句用于计算和写入值（大多是在交互模式下），或者调用一个过程 (过程就是不返回有意义结果的函数。在 Python 中，过程的返回值为 None)。

表达式语句会对指定的表达式进行求值。

在交互模式下，它会通过内置的 repr() 函数转换为一个字符串，该结果字符串将以单独一行的形式写入标准输出（例外情况是如果结果为 None，则该过程调用不产生任何输出）。

以下均是一个表达式语句（可包含多个表达式）：


```python
'python'
```




    'python'




```python
1
```




    1




```python
(a := 1) # 3.8 新功能，赋值表达式
```




    1




```python
a
```




    1




```python
'a\n',f'b{1}' # 两个表达式
```




    ('a\n', 'b1')




```python
1 + 2 * 3 / 5, True and False # 两个表达式
```




    (2.2, False)




```python
lambda x: x**2
```




    <function __main__.<lambda>(x)>




```python
0 if 2>3 else (1 if 5<6 else 2)
```




    1




```python
[1,2,3] + [4]
```




    [1, 2, 3, 4]




```python
[].append(1) # 返回 None
```


```python
[].append(1) is None
```




    True




```python
# 返回值为 None，输出并不是表达式的值
print('非表达式的值')  is None
```

    非表达式的值
    




    True




```python
sum(i for i in [3,2,5])
```




    10




```python
list(zip('abc',[1,2,3]))[1:]
```




    [('b', 2), ('c', 3)]



用分号分隔多个表达式语句，输出最后一个的值。


```python
1; print('非表达式的值'); 1 + 2 * 3 / 5, True and False
```

    非表达式的值
    




    (2.2, False)


