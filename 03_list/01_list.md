## 列表概述

列表对象 list 是高级数据结构的一种，通过方括号括起、逗号分隔的一组值得到。类型是 list。


```python
type([1,2,3])
```




    list



列表是可变序列，通常用于存放同类项目的集合。但没做限制，可以存放任意对象。


```python
[1,'a',int]
```




    [1, 'a', int]



列表是可变的，分别创建两个值相同的列表，一定是不同的对象；而同一个列表对象中的元素是可以改变的：


```python
a, b = [1,2], [1,2]
a == b
```




    True




```python
id(a), id(b)
```




    (2004948061384, 2004947934152)




```python
a[0] = 'a'
a, id(a)
```




    (['a', 2], 2004948061384)



列表创建方法有：直接用一对方括号表示；[列表推导式](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/03_list/02_list_comprehension.ipynb)；或使用内建函数 [list()](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/11_built-in_function/37_list.ipynbb)。


```python
[], [1,2]
```




    ([], [1, 2])




```python
[i for i in range(3)]
```




    [0, 1, 2]




```python
list('abc')
```




    ['a', 'b', 'c']



列表的所有切片都将得到一个新列表，这意味着以下切片操作会返回列表的一个浅拷贝:


```python
list_1 = [1,2,3]
list_2 = list_1[:]
id(list_1), id(list_2)
```




    (2004947038600, 2004948064968)



然而，列表可以利用切片改变自身的内容，列表仍然是原来的列表：


```python
list_1[:] = 'abc'
list_1, id(list_1)
```




    (['a', 'b', 'c'], 2004947038600)


