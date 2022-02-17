## range 对象

range 对象是一个整数等差数列，用内置函数 [range()](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/11_built-in_function/50_range.ipynb) 构造得到，类型是 range：


```python
type(range(3))
```




    range




```python
range(-1,5,2)
```




    range(-1, 5, 2)



range 通常用于在 for 循环中循环指定的次数：


```python
for i in range(3):
    print('重要的事情说三遍')
```

    重要的事情说三遍
    重要的事情说三遍
    重要的事情说三遍
    

range 对象可以指定起始值（默认 0），结束值（不包含），和等差数列的公差（默认 1）。

指定一个大于 0 的值则默认从 0 开始，公差为 1，到指定值之前一个整数结束：


```python
list(range(5))
```




    [0, 1, 2, 3, 4]



因为公差默认为 1，指定一个小于等于 0 的值则得到空 range：


```python
list(range(-5))
```




    []



起始值，结束值，公差都指定，则得到相应等差数列：


```python
list(range(1,5))
```




    [1, 2, 3, 4]




```python
list(range(1,-5,-1))
```




    [1, 0, -1, -2, -3, -4]



range 类型相比常规 list 或 tuple，优势在于一个 range 对象总是占用固定的（较小）内存，不论其所表示的范围有多大。因为 range 类型只保存了 start, stop 和 step 值，并会根据需要计算具体单项或子范围的值。

除了拆包可以使用操作符`*`，range 对象不可以像列表，元组等一样，使用 `+`，`*`，`+=`，`*=`进行拼接或重复：


```python
(*range(3),)
```




    (0, 1, 2)


