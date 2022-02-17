## 操作符特殊用法

容器类的内置类型，通常对操作符定义了自己特有的的操作行为。

- `*` 操作符，除了数字运算的 乘，还可以用来将可迭代对象拆包。拆包之后置于元组，列表，集合中，或作为参数传递给函数：


```python
{*{'a':1, 'b':2}}
```




    {'a', 'b'}




```python
print(*'abc', sep='-')
```

    a-b-c
    

- `+`，`+=`，`*`，`*=` 可用来对序列类型进行拼接，重复拼接或拼接并赋值（range 类型除外）。由于列表是可变对象，`+=` 和 `*=` 在操作列表时，是用来更新列表。具体详见 [列表操作符](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/03_list/04_list_operator.ipynb)。


```python
'd-' + 'abc'*2
```




    'd-abcabc'




```python
a = [1]*2
a += [2]
a
```




    [1, 1, 2]



- 操作符 `**`，`|` 和 `|=` 可以用来操作字典。具体详见 [字典操作符](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/07_dictionary/14_operator.ipynb)。

- 操作符 `>`，`<`，`>=`，`<=` 可对集合进行子集或超集比较；`|`，`&`，`-`，`^` 可求集合的并集，交集，差集，对称差集；`|=`，`&=`，`-=`，`^=` 可用来更新集合。具体详见集合知识点。

- 操作符 `%` 可以用来格式化字符串，而在**格式化迷你语言**中，定义了非常多的有特殊意义操作符。具体详见 [str.format 格式化](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/02_string/25_str.format.ipynb) 和 [字符串操作符](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/02_string/28_string_operators.ipynb)。
