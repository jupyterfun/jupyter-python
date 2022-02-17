## 名称

名称（标识符）用于指代对象。当名称被绑定到一个对象时，对该名称求值将返回相应对象。当名称未被绑定时，尝试对其求值将引发 NameError 异常。Python 的保留字或称关键字是特殊的名称，不可被用作普通名称，例如函数名，模块名。


```python
# 将 1 绑定名称 a
a = 1
a
```




    1




```python
# 将自定义类对象绑定到名称 A
class A:
    pass
A
```




    __main__.A




```python
# 将模块 random 绑定到名称 r
import random as r
r
```




    <module 'random' from 'F:\\anaconda\\lib\\random.py'>




```python
# 迭代的每一项循环绑定到名称 i
for i in 'xue':
    display(i)

i
```


    'x'



    'u'



    'e'





    'e'




```python
# 未绑定的名称 m
m
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-4-2469ef96c490> in <module>
          1 # 未绑定的名称 m
    ----> 2 m
    

    NameError: name 'm' is not defined



```python
help('keywords') # 保留字
```

    
    Here is a list of the Python keywords.  Enter any keyword to get more help.
    
    False               class               from                or
    None                continue            global              pass
    True                def                 if                  raise
    and                 del                 import              return
    as                  elif                in                  try
    assert              else                is                  while
    async               except              lambda              with
    await               finally             nonlocal            yield
    break               for                 not                 
    
    


```python
False = 0
```


      File "<ipython-input-9-223dbc74e028>", line 1
        False = 0
        ^
    SyntaxError: cannot assign to False
    


检查一个名称是否有效可用字符串方法 str.isidentifier()：


```python
'for'.isidentifier()
```




    True




```python
'my_name'.isidentifier()
```




    True




```python
'函数'.isidentifier()
```




    True



普通名称命名规则：
- 可以使用大部分非标点符号的 Unicode 字符，但请使用 ASCII 范围内 (U+0001..U+007F) 的字符；
- 习惯使用大写和小写字母 A 至 Z，下划线 _ 以及数字 0 至 9，但不可以数字打头；
- 长度没有限制，对大小写敏感。


```python
数字一 = 1
数字一
```




    1




```python
def 函数():
    pass
函数
```




    <function __main__.函数()>



命名模式以下划线字符打头和结尾，有特殊含义的名称（`*` 代表任意数量可用名称字符）:

- `_*` 不会被 `from module import *` 导入。特殊标识符 `_` 在交互式解释器中被用来存放最近一次求值结果；它保存在 builtins 模块中。当不处于交互模式时，`_` 无特殊含义也没有预定义。

- `__*__` 系统定义的名称，这些名称是由解释器及其实现（包括标准库）定义的特殊属性和方法名称。未来的 Python 版本中还将定义更多此类名称。任何情况下任何不遵循文档所显式指明的 `__*__` 名称使用方式都可能导致无警告的错误。

- `__*` 类的私有名称。这种名称在类定义中使用时，会以一种混合形式重写以避免在基类及派生类的 “私有” 属性之间出现名称冲突。例如，出现在一个名为 `Ham` 的类中的名称 `__spam` 会被转换为 `_Ham__spam`。如果类名仅由下划线组成，则不会进行转换。


```python
b = 100
b
```




    100




```python
_
```




    100




```python
dir(object)
```




    ['__class__',
     '__delattr__',
     '__dir__',
     '__doc__',
     '__eq__',
     '__format__',
     '__ge__',
     '__getattribute__',
     '__gt__',
     '__hash__',
     '__init__',
     '__init_subclass__',
     '__le__',
     '__lt__',
     '__ne__',
     '__new__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__setattr__',
     '__sizeof__',
     '__str__',
     '__subclasshook__']




```python
class B:
    __b = 0
dir(B)
```




    ['_B__b',
     '__class__',
     '__delattr__',
     '__dict__',
     '__dir__',
     '__doc__',
     '__eq__',
     '__format__',
     '__ge__',
     '__getattribute__',
     '__gt__',
     '__hash__',
     '__init__',
     '__init_subclass__',
     '__le__',
     '__lt__',
     '__module__',
     '__ne__',
     '__new__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__setattr__',
     '__sizeof__',
     '__str__',
     '__subclasshook__',
     '__weakref__']



del 语句可删除名称绑定：


```python
c = 3
print(f'c={c}')
del c
c
```

    c=3
    


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-23-5ba97d2f3254> in <module>
          2 print(f'c={c}')
          3 del c
    ----> 4 c
    

    NameError: name 'c' is not defined

