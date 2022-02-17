## 导入操作

导入操作使用 import 语句，详细的语法规则查看 [import 导入语句](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/10_statement/18_import.ipynb)。

- `import ...` 只能导入模块：


```python
import random as r, pandas.core as pc
r, pc
```




    (<module 'random' from 'F:\\anaconda\\lib\\random.py'>,
     <module 'pandas.core' from 'F:\\anaconda\\lib\\site-packages\\pandas\\core\\__init__.py'>)




```python
# 导入方法报错
import random.randint
```


    ---------------------------------------------------------------------------

    ModuleNotFoundError                       Traceback (most recent call last)

    <ipython-input-2-8d4ecd1fe339> in <module>
          1 # 导入方法报错
    ----> 2 import random.randint
    

    ModuleNotFoundError: No module named 'random.randint'; 'random' is not a package


- `from ... import ...` 从模块中导入子模块，类，函数等： 


```python
from pandas import core
core
```




    <module 'pandas.core' from 'F:\\anaconda\\lib\\site-packages\\pandas\\core\\__init__.py'>




```python
from pandas import DataFrame as df
df
```




    pandas.core.frame.DataFrame




```python
from random import randint
randint
```




    <bound method Random.randint of <random.Random object at 0x000001E44ED52020>>




```python
from math import pi
pi
```




    3.141592653589793



- `from ... import *` 将导入模块中所有的公有属性：

例如，如果在文件 `mycode/__init__.py` 中我们定义了属性 `__all__` ，从包 `mycode` 导入则只能导入该属性中的名称；在文件 `mycode/mycode.py` 中，以下划线打头的属性名，从模块 `mycode.mycode` 导入时都不可导入。

通常情况下不应使用这个功能，因为它在解释器中引入了一组未知的名称，而它们很可能会覆盖一些你已经定义过的名称。而且会导致代码的可读性很差。


```python
# mycode/__init__.py
__all__ = ['mycode','xue']
```


```python
# mycode/mycode.py
_a = '自学'

def __f():
    print(_a)

print('mycode')

from mycode import xue

if __name__ == '__main__':
    print(xue.msg)
```


```python
from mycode import *
mycode, xue
```




    (<module 'mycode.mycode' from 'E:\\xue\\脚本\\kp_book\\15_module\\mycode\\mycode.py'>,
     <module 'mycode.xue' from 'E:\\xue\\脚本\\kp_book\\15_module\\mycode\\xue.py'>)




```python
from mycode.mycode import *
_a
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-14-e68848edb46a> in <module>
          1 from mycode.mycode import *
    ----> 2 _a
    

    NameError: name '_a' is not defined



```python
__f
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-15-004321bbfec5> in <module>
    ----> 1 __f
    

    NameError: name '__f' is not defined



```python
# 其他方式则可以导入
from mycode.mycode import __f
print(__f)
del __f
```

    <function __f at 0x000001E45129B430>
    

- 相对导入：

存在相对导入代码的模块，通常是不能直接执行的。因为直接执行，解释器认为该模块即为顶级模块，属性 `__package__` 的值为 None。但可以使用 `python -m 模块` 命令直接执行。


```python
print(__package__)
```

    None
    

例如，当前文件路径下，文件 `mycode/test.py` 中相对导入的代码可以使用 `python -m 模块` 命令直接执行，因为该命令将属性 `__package__` 重新设置为顶级模块的名称：


```python
# xue.py 模块在 mycode 包中
# mycode/test.py
from . import xue
print(xue.msg)
print(__package__)
```


```python
%run -m mycode.test
```

    自学是门手艺
    mycode
    

模块导入之后，即可使用属性表示法调用模块中属性：


```python
import random, math
random.randint, math.pi
```




    (<bound method Random.randint of <random.Random object at 0x000002811CF98C80>>,
     3.141592653589793)


