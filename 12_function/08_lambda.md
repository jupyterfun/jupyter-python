## lambda 函数

lambda 函数由 lambda 表达式创建，表达式的语法为：
```
 lambda parameters: expression
```
形参 `parameters` 是可选的，表达式 `expression` 会在函数调用时被求值并作为返回值返回。

表达式必须显示地确定为一个表达式，而不能像 return 语句那样返回多个表达式（默认为一个元组）。

lambda 表达式会创建一个没有名字的函数，函数不能包含语句或标注，可以像调用函数一样直接调用它。


```python
(lambda x,y: x**y)(2,3)
```




    8




```python
lambda x,y: x**y
```




    <function __main__.<lambda>(x, y)>




```python
# 返回值必须显示地确定为一个表达式
f = lambda x: sum(x),max(x),min(x)
f([2,3,4])
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-5-1652333b2bc4> in <module>
          1 # 必须显示地确定为一个表达式
    ----> 2 f = lambda x: sum(x),max(x),min(x)
          3 f([2,3,4])
    

    NameError: name 'x' is not defined



```python
f = lambda x: (sum(x),max(x),min(x))
f([2,3,4])
```




    (9, 4, 2)



lambda 函数通常在以函数作为参数的高阶函数中使用，没有名称，用完即弃。


```python
a = ['2  2', '2 1 ','2  3']
sorted(a,key=lambda x:''.join(x.split()))
```




    ['2 1 ', '2  2', '2  3']




```python
list(map(lambda x:''.join(x.split()), a))
```




    ['22', '21', '23']


