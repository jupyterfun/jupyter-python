## 其他内置类型

内置类型除了数字类型，布尔类型，序列类型，集合类型，映射类型，迭代器类型，解释器支持的还有一些其他种类的对象。这些对象大都仅支持一两种操作。

### 模块

模块唯一的特殊操作是属性访问: `m.name`，这里 m 为一个模块而 name 为定义在 m 的符号表中的一个属性的名称。模块属性可以被赋值。import 语句严格来说也是对模块对象的一种操作。关于模块有详细的知识点介绍。


```python
type(math)
```




    module




```python
import math
math.pi
```




    3.141592653589793



### 函数

函数对象是通过函数定义创建的。对函数对象的唯一操作是调用它: func(argument-list)。

实际上存在两种不同的函数对象：内置函数和用户自定义函数。两者支持同样的操作（调用函数），但实现方式不同，因此对象类型也不同。关于函数有详细的知识点介绍。


```python
print('abc') # 调用函数
```

    abc
    


```python
type(print)
```




    builtin_function_or_method




```python
def f():pass # 自定义函数
type(f)
```




    function



### 方法

方法是在类中定义，使用属性表示法来调用的函数。关于方法有详细的知识点介绍。


```python
type(list.append)
```




    method_descriptor




```python
type([].append)
```




    builtin_function_or_method



### 代码对象

代码对象可由内置的 [compile()](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/11_built-in_function/11_compile.ipynb) 函数返回，也可通过从函数对象的 `__code__` 属性从中提取。

可将代码对象（而非源码字符串）传给 [exec()](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/11_built-in_function/19_exec.ipynb) 或 [eval()](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/11_built-in_function/18_eval.ipynb) 内置函数来执行或求值。


```python
def f():
    print('代码对象')
code = f.__code__
type(code)
```




    code




```python
exec(code)
```

    代码对象
    

### 类型对象

类型对象表示各种对象类型。对象的类型可通过内置函数 [type()](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp) 来获取。类型没有特殊的操作。标准库模块 types 定义了所有标准内置类型的名称。


```python
type(int), type(list)
```




    (type, type)




```python
type(1), type([])
```




    (int, list)


