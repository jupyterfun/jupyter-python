## 生成器表达式和推导式

生成器表达式和列表推导式非常相似，区别就是将方括号换成了小括号。

生成器表达式返回的是一个生成器迭代器 generator。表达式会产生一系列值，可使用内置函数 [next()](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/11_built-in_function/42_next.ipynb) 逐一获取，或使用 for 循环遍历。

生成器迭代器中的元素，仅供一次性使用，而且可以要多少取多少，它会记住你取了多少，取到了哪里。


```python
(i*i for i in range(3))
```




    <generator object <genexpr> at 0x00000271080FBC00>




```python
g = (i*i for i in range(5))
type(g)
```




    generator




```python
next(g), next(g)
```




    (0, 1)




```python
for i in g:
    print(i)
```

    4
    9
    16
    

这种表达式被设计用于生成器将立即被外层函数所使用的情况。生成器表达式相比完整的生成器更紧凑但较不灵活，相比等效的列表推导式则更为节省内存。


```python
sum(i*i for i in range(5))
```




    30




```python
list(i*i for i in range(5))
```




    [0, 1, 4, 9, 16]



除了列表推导式和生成器表达式，集合和字典也可使用类似的推导式。


```python
{i*2 for i in 'abac'}
```




    {'aa', 'bb', 'cc'}




```python
{i:j for i,j in zip('abc',(1,2,3))}
```




    {'a': 1, 'b': 2, 'c': 3}


