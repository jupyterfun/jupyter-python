## 字典操作符

字典不可以使用比较大小的操作符 `<`, `<=`, `>=` 和 `>`，会引发 TypeError。


```python
{1:1} < {2:2}
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-1-8ea82599b938> in <module>
    ----> 1 {1:1} < {2:2}
    

    TypeError: '<' not supported between instances of 'dict' and 'dict'


字典比较相等时，当且仅当 键值对 都相等时才相等。


```python
{1:1.0, 2:2} == {2:2, True:1}
```




    True




```python
{1:'1', 2:2} == {2:2, 1:1}
```




    False



字典可以使用 `**` 操作符进行拆包，拆包后置于新字典中，可以用来更新字典；或拆包后作为关键字参数传递给函数。


```python
{'a':1, 'b':2, **{'a':10}}
```




    {'a': 10, 'b': 2}




```python
d = {'a':1, 'b':2}
'a={a},b={b}'.format(**d)
```




    'a=1,b=2'



Python 3.9 新版，实现了两个操作符 `|` 和 `|=`：

- d | other

合并 d 和 other 中的键和值来创建一个新的字典，两者必须都是字典。当 d 和 other 有相同键时，other 的值优先。

- d |= other

用 other 的键和值更新字典 d ，other 可以是映射（mapping）或可迭代对象（iterable）的键值对。当 d 和 other 有相同键时，other 的值优先。
