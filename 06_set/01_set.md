## 集合概述

集合是由具有唯一性的可哈希对象（一个对象的哈希值如果在其生命周期内绝不改变）组成的无序多项集。

目前有两种内置集合类型，set 和 frozenset，前者是可变类型，后者是不可变类型。


```python
type({1}), type(frozenset())
```




    (set, frozenset)



因为一对花括号表示字典而非集合，所以创建空集合必须使用构造函数 [set()](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/11_built-in_function/54_set.ipynb) 和 [frozenset()](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/11_built-in_function/23_frozenset.ipynb) 来表示。两个内置函数还可将可迭代对象转换为集合：


```python
type({}), set(), frozenset()
```




    (dict, set(), frozenset())




```python
set('121'), frozenset('112')
```




    ({'1', '2'}, frozenset({'1', '2'}))



构造 set 集合还可以直接使用一对花括号包含元素，元素之间用逗号隔开：


```python
{1,2,1}
```




    {1, 2}



集合的元素必须是可哈希的，例如字符串，元组（不能包含不可哈希对象，例如元组里有列表）；也是唯一的，同时存在多个哈希值相等的元素，只保留一个。


```python
print(hash(False),hash(0))
```

    0 0
    


```python
{'12', (1,2), False, 0}
```




    {(1, 2), '12', False}



set 类型集合是可变类型，没有哈希值，不可作为集合的元素或字典的键，而 frozenset 类型的集合可以：


```python
{frozenset([1,2])}
```




    {frozenset({1, 2})}



两种类型集合可进行比较，并集，交集，差集，对称差集操作：


```python
{1,2} == frozenset({1,2})
```




    True




```python
{1,2} | frozenset({1,2,3})
```




    {1, 2, 3}




```python
frozenset({1,2,3}) ^ {1,2}
```




    frozenset({3})



set 类型是可变的，还可进行元素增、删、改，等操作，而 frozenset 类型不可以：


```python
a = set()
print(id(a))
# a 增加元素 1
a.add(1)
print(id(a),a)
# 将一个集合并入 a
a |= frozenset({1,2,3})
print(id(a),a)
# 清空集合 a
a.clear()
print(id(a),a)
```

    2029775797832
    2029775797832 {1}
    2029775797832 {1, 2, 3}
    2029775797832 set()
    

集合是按哈希值对元素进行储存，而不是按顺序，因此集合没有索引和切片操作。搜索元素时，由于是通过哈希值匹配，集合比序列类型效率高。

由于集合仅定义了部分排序（子集关系），比较大小的排序并无定义。


```python
{2,1,5} > {2,5}
```




    True




```python
a = [{2,1,5},{9},{6},{2,5}]
a.sort() 
a
```




    [{1, 2, 5}, {9}, {6}, {2, 5}]


