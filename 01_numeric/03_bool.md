## 布尔值及布尔运算

布尔值有 True 和 False，布尔类型是整数类型的子类型，所以整数的运算都适用布尔值运算。


```python
issubclass(bool,int)
```




    True




```python
True + 1
```




    2




```python
~True
```




    -2



任何对象都可以进行布尔值的检测，以便在 if 或 while 中作为条件或是作为下文所述布尔运算的操作数来使用。

一个对象在默认情况下均被视为真值，除非当该对象被调用时其所属类定义了 `__bool__()` 方法且返回 False 或是定义了 `__len__()` 方法且返回零。

下面基本完整地列出了会被视为假值的内置对象:
- 被定义为假值的常量: None 和 False。
- 任何数值类型的零: 0, 0.0, 0j, Decimal(0), Fraction(0, 1)
- 空的序列和多项集: '', (), [], {}, set(), range(0)

可以使用内置函数 bool() 来查看任意对象的布尔值：


```python
bool(None), bool(int), bool(0)
```




    (False, True, False)



## 布尔运算

布尔运算按优先级升序排列：
- `x or y`, if x is false, then y, else x 
- `x and y`, if x is false, then x, else y 
- `not x`, if x is false, then True, else False 

任何值（包括表达式求值结果），除了自身之外，还有相应的逻辑值（布尔值），所以布尔运算符 or，and，not 可对任何值进行运算。

举例如下：


```python
1>2 or 'python'
```




    'python'



1>2 表达式结果为 False，所以布尔运算结果为 'python'。


```python
1+1 or 'python'
```




    2



1+1 表达式结果为 2，布尔值为 True，所以布尔运算结果为 2。


```python
1>2 and 'python'
```




    False



1>2 表达式的结果为 False，所以布尔运算结果为 False。


```python
1<2 and 'python'
```




    'python'



1<2 表达式的结果为 True，所以布尔运算结果为 'python'。


```python
not 'python'
```




    False



'python' 的布尔值为 True，所以布尔运算结果为 False。


```python
not 0
```




    True



0 的布尔值为 False，所以布尔运算结果为 True。
