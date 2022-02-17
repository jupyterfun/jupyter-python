## 比较运算符

比较运算符有 `<`，`>`，`<=`，`>=`，`==`，`!=`，`in`，`not in`，`is`，`is not`。

运算符 `<`，`>`，`>=`，`<=`，`==` 和 `!=` 比较两个对象的值，`<`，`>`，`>=` 和 `<=` 称为次序比较；`==` 和 `!=` 称为一致性比较。

由于所有类型都是 object 的（直接或间接）子类型，它们都从 object 继承了默认的比较行为，一致性比较是默认的比较行为，因此可在任何对象之间进行。


```python
False == 0 != 'a' != int != {}
```




    True



对象的值在 Python 中是一个相当抽象的概念：
- 对象的值并没有一个规范的访问方法；
- 对象的值并不要求具有特定的构建方式，例如由其全部数据属性组成等；
- 比较运算符实现了一个特定的对象的值概念，可以认为正是通过实现对象比较，间接地定义了对象的值。

主要内置类型的比较行为：

1，数字类型内部可跨类型比较，按数学（算法）规则正确进行比较且不会有精度损失。但复数不支持次序比较。


```python
True == 1 == 1.0
```




    True




```python
3.14 < 3
```




    False




```python
0 >= 0j
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-6-df80cad0b1a4> in <module>
    ----> 1 0 >= 0j
    

    TypeError: '>=' not supported between instances of 'int' and 'complex'


2，字符串使用其字符的 Unicode 码位数字值依次进行比较，某个字符比较出大小即停止。如果一个字符串包含另一个，较短的排前面。


```python
ord('a'), ord('b'), ord('c')
```




    (97, 98, 99)




```python
'a' == 'a', 'a' == 'c'
```




    (True, False)




```python
'ab' < 'ac'
```




    True




```python
'abc' > 'ab'
```




    True



3，序列（列表，元组，range 实例）只能进行类型内部比较。跨类型一致性比较结果将是不相等，跨类型次序比较将引发 TypeError。range 不支持次序比较。

比较时按顺序对相应元素进行逐个比较，某个元素比较出大小即停止。如果一个序列元素包含另一个，较短的排前面。


```python
(1,2) == [1,2]
```




    False




```python
[1,2] == [1,2]
```




    True




```python
[1,4] > [1,3,7]
```




    True




```python
[1,4] < [1,4,7]
```




    True




```python
(1,2) >= [1,2]
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-22-cb12354bca8e> in <module>
    ----> 1 (1,2) >= [1,2]
    

    TypeError: '>=' not supported between instances of 'tuple' and 'list'


4， 两个字典若要相等，必须当且仅当它们具有相同的 键值对。次序比较将引发 TypeError。


```python
{1:1} == {True:1.0}
```




    True




```python
{1:1} <= {True:1.0}
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-24-a13e7674e543> in <module>
    ----> 1 {1:1} <= {True:1.0}
    

    TypeError: '<=' not supported between instances of 'dict' and 'dict'


5，集合 (set 或 frozenset 的实例) 可进行类型内部和跨类型的比较。

它们将比较运算符定义为子集和超集检测，具体详见集合知识点。这类关系没有定义完全排序。相应地，集合不适宜作为依赖于完全排序的函数的参数。


```python
{1,2} == frozenset([1,2,1])
```




    True




```python
{3,1} > {1,2}
```




    False




```python
sorted([{3},{1},{2}])
```




    [{3}, {1}, {2}]



运算符 `in` 和 `not in` 用于成员检测。如果 x 是 s 的成员则 `x in s` 求值为 True，否则为 False。`x not in s` 返回 `x in s` 取反后的值。

所有内置序列和集合类型以及字典都支持此运算，对于字典来说 in 检测其是否有给定的键。


```python
'a' in 'abc'
```




    True




```python
'abc' in 'abbc'
```




    False




```python
1 in [1,2]
```




    True




```python
[1] in [1,2]
```




    False




```python
'a' in {'a':1}
```




    True



运算符 `is` 和 `is not` 用于检测对象的标识号：当且仅当 x 和 y 是同一对象时 `x is y` 为真。一个对象的标识号可使用 id() 函数来确定。`x is not y` 会产生相反的逻辑值。 

默认的一致性比较是基于对象的标识号。`x is y` 就意味着 `x == y`。


```python
a = 1
b = 1
a is b, a == b
```




    (True, True)




```python
a = (1,3)
b = (1,3)
a is b, a == b
```




    (False, True)


