## 数字类型概述

数字类型属于内置类型。有三种不同的数字类型：整数，浮点数和复数。

整数通常只有数字，浮点数有小数点，而复数有实部（省略则为 0）和虚部，虚部必须有 J 或 j。

它们的类型分别是 int，float 和 complex。


```python
type(1), type(1.0), type(1j)
```




    (int, float, complex)



它们虽然属于不同的类型，但 Python 完全支持其混合运算。

而且布尔类型属于整数类型的子类型，布尔类型也可参与混合运算。


```python
True/3 + 1.5 - 1J
```




    (1.8333333333333333-1j)



数字之间比较时，比较的是它们的精度决定的精确值：


```python
True == 1 == 1.0
```




    True



对于不同类型的数字，只要精确值相等，哈希值必定相等：


```python
hash(True) == hash(1) == hash(1.0)
```




    True



因此作为集合的元素时，它们是一个元素；作为字典的键时，是同一个键。但这不是明智之举，因为浮点数存在精度问题：


```python
{True, 1, 1.0}
```




    {True}




```python
{True:1, 1:2, 1.0:3}
```




    {True: 3}




```python
1.00000000000000009 == 1
```




    True



整数，浮点数和复数的构造函数分别是：[int()](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/11_built-in_function/32_int.ipynb)，[float()](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/11_built-in_function/21_float.ipynb) 和 [complex()](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/11_built-in_function/12_complex.ipynb)。构造细节详见相应内置函数知识点。


```python
int('1'), float('1.0'), complex('1')
```




    (1, 1.0, (1+0j))



关于各数字类型的特性和详细介绍见后面章节。
