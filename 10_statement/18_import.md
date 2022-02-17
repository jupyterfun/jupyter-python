## import 导入语句

import 语句用于从模块中导入子模块，类，函数等。语法大致有三种：
```
# 第一种
import module as name, module as name, ...

# 第二种
# import 之后可以置于一个元组
from module import identifier as name, identifier as name, ...

# 第三种
from module import *
```

模块 `module` 可以是高层级到低层级用属性表示法引用的模块，例如 `pandas.core.series`。

`as` 及其后的别名 `name` 是可选的。

语句可以导入单个或多个对象，用逗号分隔实际是多个子句。

第一种导入方法，如果成功获取到模块，则可以通过以下方式之一在 import 语句所在命名空间中使用它：
- 如果被导入模块是最高层级模块，模块名被绑定；
- 如果导入的模块不是最高层级的模块，则该模块的最高层级模块名被绑定，该模块必须使用完整限定名访问；
- 如果有 as，则 as 之后的别名被绑定，模块名不绑定。

如果没有指定模块，引发 ModuleNotFoundError。


```python
import pandas
pandas
```




    <module 'pandas' from 'F:\\anaconda\\lib\\site-packages\\pandas\\__init__.py'>




```python
del pandas
import pandas.core.series
pandas, pandas.core, pandas.core.series
```




    (<module 'pandas' from 'F:\\anaconda\\lib\\site-packages\\pandas\\__init__.py'>,
     <module 'pandas.core' from 'F:\\anaconda\\lib\\site-packages\\pandas\\core\\__init__.py'>,
     <module 'pandas.core.series' from 'F:\\anaconda\\lib\\site-packages\\pandas\\core\\series.py'>)




```python
series # 必须完成限定名访问
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-6-2859777d6f2b> in <module>
    ----> 1 series
    

    NameError: name 'series' is not defined



```python
del pandas
import pandas.core.series as pds
pds
```




    <module 'pandas.core.series' from 'F:\\anaconda\\lib\\site-packages\\pandas\\core\\series.py'>




```python
pandas # 只能使用别名访问
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-8-609b6d5922fb> in <module>
    ----> 1 pandas
    

    NameError: name 'pandas' is not defined



```python
def f():
    import pandas # 局部命名空间导入
pandas # 全局命名空间不能访问
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-10-0b76d1984901> in <module>
          1 def f():
          2     import pandas # 局部命名空间导入
    ----> 3 pandas
    

    NameError: name 'pandas' is not defined


第二种导入方法，如果成功获取到模块，from 之后的模块名不会被绑定，对于 import 子句导入的属性或子模块，如果有 as 子句，则只能使用其指定的别名使用它，否则使用该属性或子模块的名称 identifier 使用它。

如果属性或子模块不存在，或不能导入，引发 ImportError。


```python
from pandas.core import base
base
```




    <module 'pandas.core.base' from 'F:\\anaconda\\lib\\site-packages\\pandas\\core\\base.py'>




```python
pandas.core # 只导入了该模块下的子模块 base
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-2-37462de79a89> in <module>
    ----> 1 pandas.core
    

    NameError: name 'pandas' is not defined



```python
# 导入多个可置于元组中
from random import (random as r1,
                    randint as r2,)
r1, r2
```




    (<function Random.random()>,
     <bound method Random.randint of <random.Random object at 0x000001E531A14580>>)




```python
# pandas 下没有 base，导入错误
from pandas import base 
```


    ---------------------------------------------------------------------------

    ImportError                               Traceback (most recent call last)

    <ipython-input-7-7903c4949085> in <module>
    ----> 1 from pandas import base
    

    ImportError: cannot import name 'base' from 'pandas' (F:\anaconda\lib\site-packages\pandas\__init__.py)


第三种导入方法，则在模块中定义的全部公有名称都将绑定到 import 语句所在的命名空间。

公有名称是由在模块的命名空间中检测一个名为 `__all__` 的变量来确定的；如果 `__all__` 没有被定义，则公有名称的集合将包含模块的命名空间中找到的所有不以下划线字符 `_` 打头的名称。


```python
from random import *
randint
```




    <bound method Random.randint of <random.Random object at 0x0000025E1DCC8180>>



当指定要导入哪个模块时，你不必指定模块的绝对名称。当一个模块或包被包含在另一个包之中时，可以在同一个最高层级包中进行相对导入，而不必提及包名称。

通过在 from 之后指定的模块或包中使用前缀点号，你可以在不指定确切名称的情况下指明在**当前包**层级结构中要上溯多少级。一个前缀点号表示是执行导入的模块所在的当前包，两个点号表示上溯一个包层级。三个点号表示上溯两级，依此类推。例如：
```
package/
    __init__.py
    subpackage1/
        __init__.py
        moduleX.py
        moduleY.py
    subpackage2/
        __init__.py
        moduleZ.py
    moduleA.py
```
假设当前位置是 ` subpackage1/moduleX.py`，则：
```
from .moduleY import spam
from . import moduleY
from ..subpackage1 import moduleY
from ..subpackage2.moduleZ import eggs
from ..moduleA import foo
```
都是有效的。
