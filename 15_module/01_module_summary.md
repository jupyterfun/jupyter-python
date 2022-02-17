## 模块概述

模块是 Python 代码的一种组织单位，也是一种对象。各模块具有独立的命名空间，可包含任意 Python 对象。

一个 `.py` 文件是一个模块；一个文件夹是一个模块（包）；文件夹（包）中还可以再有 `.py` 文件（子模块）和文件夹（子包）。例如 内置模块 random，和第三方包 pandas。

文件夹中包含一个 `__init__.py` 文件的包是常规包；无 `__init__.py` 文件的是命名空间包，仅被用作子包的容器。

模块无论是用 Python、C 还是别的语言实现均可。


```python
import random, pandas
type(random), type(pandas)
```




    (module, module)



所有包都是模块，但并非所有模块都是包。或者换句话说，包只是一种特殊的模块。

可以使用属性 `__packge__` 查看包名，如果只是模块不是包，该属性为空字符串。

`__name__` 属性是模块的名字。

特别地，主模块（你正在运行代码的当前模块）的 `__packge__` 属性总是 None；`__name__` 属性总是 `'__main__'` （`__main__` 是一个在解释器启动时直接初始化的特殊模块），这可以控制当前模块能够执行，而导入到其他模块不能被执行的代码，然后用来测试当前模块。


```python
random.__package__, pandas.__package__
```




    ('', 'pandas')




```python
print(__package__)
```

    None
    


```python
random.__name__, pandas.__name__
```




    ('random', 'pandas')




```python
__name__
```




    '__main__'




```python
a = 3 + 2 - 5
def f():
    print(a+1)
print(a)

if __name__ == '__main__':
    # 以下代码导入其他模块不会执行
    print(a == 0)
```

    0
    True
    

使用 import 语句将其他模块导入当前模块；使用属性表示法调用模块中的属性。


```python
import pandas as pd
pd.core
```




    <module 'pandas.core' from 'C:\\ProgramData\\Anaconda3\\lib\\site-packages\\pandas\\core\\__init__.py'>




```python
pd.core.series.Series
```




    pandas.core.series.Series



还可以以脚本的方式执行不属于包的模块（此时 `__name__` 属性为 `"__main__"`）。


```python
import this
this
```

    The Zen of Python, by Tim Peters
    
    Beautiful is better than ugly.
    Explicit is better than implicit.
    Simple is better than complex.
    Complex is better than complicated.
    Flat is better than nested.
    Sparse is better than dense.
    Readability counts.
    Special cases aren't special enough to break the rules.
    Although practicality beats purity.
    Errors should never pass silently.
    Unless explicitly silenced.
    In the face of ambiguity, refuse the temptation to guess.
    There should be one-- and preferably only one --obvious way to do it.
    Although that way may not be obvious at first unless you're Dutch.
    Now is better than never.
    Although never is often better than *right* now.
    If the implementation is hard to explain, it's a bad idea.
    If the implementation is easy to explain, it may be a good idea.
    Namespaces are one honking great idea -- let's do more of those!
    




    <module 'this' from 'C:\\ProgramData\\Anaconda3\\lib\\this.py'>




```python
# %run 是 jupyter 的魔法命令，在终端使用 python 命令
# F:\anaconda\lib\this.py 根据自己电脑的路径调整
%run F:\anaconda\lib\this.py
```

    The Zen of Python, by Tim Peters
    
    Beautiful is better than ugly.
    Explicit is better than implicit.
    Simple is better than complex.
    Complex is better than complicated.
    Flat is better than nested.
    Sparse is better than dense.
    Readability counts.
    Special cases aren't special enough to break the rules.
    Although practicality beats purity.
    Errors should never pass silently.
    Unless explicitly silenced.
    In the face of ambiguity, refuse the temptation to guess.
    There should be one-- and preferably only one --obvious way to do it.
    Although that way may not be obvious at first unless you're Dutch.
    Now is better than never.
    Although never is often better than *right* now.
    If the implementation is hard to explain, it's a bad idea.
    If the implementation is easy to explain, it may be a good idea.
    Namespaces are one honking great idea -- let's do more of those!
    
