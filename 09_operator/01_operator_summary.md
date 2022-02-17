## 操作符概述

操作符可分为**运算符**（operators）和**分隔符**（delimiters）。

运算符有：

- 数字运算符

`+`，`-`，`*`，`**`，`/`，`//`，`%`，详细用法见 [数字运算](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/01_numeric/06_number_operations.ipynb)。

- 整数按位运算符

`<<`，`>>`，`&`，`|`，`^`，`~`，详细用法见 [整数及其位运算](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/01_numeric/02_int.ipynb)。

- 比较运算符

`<`，`>`，`<=`，`>=`，`==`，`!=`，`in`，`not in`，`is`，`is not`，详细用法见 [比较运算符](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/09_operator/02_compare.ipynb)。

- 布尔运算符

`and`，`or`，`not`，详细用法见 [布尔值及布尔运算](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/01_numeric/03_bool.ipynb)。

- 赋值运算符 `:=`

Python 3.8 新增，将右边的表达式赋值给左边的变量， 同时返回表达式的值。


```python
(a := 1+1)
```




    2



运算符还分为一元运算符和二元运算符，一元运算符运算一个对象（操作数），二元运算符运算两个。一元运算符有 `+`（正数），`-`（负数），`~`（整数按位取反）和 `not`（布尔运算 非）。`if ... else ...` 有时称作三元运算符。


```python
-1, +2, ~3, not 4
```




    (-1, 2, -4, False)




```python
1 + 2 - 3 * 4 # 二元运算符加、减和乘
```




    -9




```python
True if 2 > 3 else False
```




    False



分隔符有：

`(`，`)`，`[`，`]`，`{`，`}`，`,`，`:`，`.`，`;`，`=`，`+=`，`-=`，`*=`，`/=`，`//=`，`%=`，`&=`，`|=`，`^=`，`>>=`，`<<=`，`**=`

部分分隔符用法举例：

圆括号绑定表达式，或元组显示，方括号用来对序列进行索引、切片取值或列表显示，花括号字典显示或集合显示


```python
3 * (1 + 2) * (1,)
```




    (1, 1, 1, 1, 1, 1, 1, 1, 1)




```python
[1,2,3,4][1:3]
```




    [2, 3]




```python
{'列表':[], '集合':{1,2,3}}
```




    {'列表': [], '集合': {1, 2, 3}}



上述分隔符 `=` 为赋值操作符，之后的操作符为增强赋值操作符，将名称绑定（或重新绑定）到特定值，以及修改属性或可变对象的成员项。 详见 [赋值语句](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/10_statement/02_assignment.ipynb)。

假设将值 value1 绑定到名称 name，`name = value1`，则 `name += value2` 的结果相当于 `name = name + value2`，其他操作符类似。

举例如下：


```python
a = 1
a += 1
a
```




    2




```python
b = 17
b |= 5
b
```




    21



除了运算符和分隔符，还有 `'`，`"`，`\`，`#` 字符，作为其他字符的组成部分时具有特殊含义，或是对词法分析器有重要意义。

`'`，`"`，`\`，详见 [字符串概述](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/02_string/01_string.ipynb) 和 [转义字符](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/02_string/03_escape_character.ipynb)。

`#` 通常用来注释代码，但不能包含在字符串中，注释在语法分析中会被忽略：


```python
# 这是注释
'''
# hello world
# hello python
'''
```




    '\n# hello world\n# hello python\n'



操作符除了常规的用法，操作不同的数据类型，相应的数据类型可能定义了特定的操作规则；在特定的应用场景，也有着特殊的用法。详见 [操作符特殊用法](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/09_operator/04_special.ipynb)
