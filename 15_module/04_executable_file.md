## 可执行文件

每一个 `.py` 文件模块，都是 Python 的可执行文件。文件内容可以为空，但执行什么也不发生。

你可以在某些编辑工具里打开文件执行，也可以在命令行使用 `python 文件路径` 或 `python -m 模块` 的方式执行。这些方式都是主模块中直接执行文件。

主模块（你正在运行代码的当前模块）的 `__name__` 属性总是 `'__main__'` （`__main__` 是一个在解释器启动时直接初始化的特殊模块），因此直接执行文件，`if __name__ == '__main__':` 语句下的代码一定会被执行，而如果导入到其他模块则不会。


```python
__name__
```




    '__main__'



下面举例说明：

当前文件路径下，有一个 `mycode` 的包，包里有 `space.py`，`mycode.py` 和 `xue.py`，三个模块，内容如下：


```python
# space.py 为空
```


```python
# mycode.py
print('mycode')

from mycode import xue

if __name__ == '__main__':
    print(xue.msg)
```

    mycode
    自学是门手艺
    


```python
# xue.py
msg = '自学是门手艺'
```

直接执行效果如上。下面使用命令执行（`%run` 是 jupyter 的魔法命令，终端请改为 `python`）：


```python
# 文件路径必须带 .py，可以是相对或绝对路径
%run mycode/space.py 
```


```python
%run mycode/mycode.py
```

    mycode
    自学是门手艺
    


```python
import warnings # 忽略警告
warnings.filterwarnings("ignore") 

# 模块可以使用属性表示法，但不能有 .py
%run -m mycode.mycode 
```

    mycode
    自学是门手艺
    


```python
# 导入则不会执行 if __name__ == '__main__': 语句下的代码
import mycode.mycode
```

    mycode
    
