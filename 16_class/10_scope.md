## 作用域

作用域定义了一个代码块中名称的可见性。如果代码块中定义了一个局部变量，则其作用域包含该代码块。如果定义发生于函数代码块中，则其作用域会扩展到该函数所包含的任何代码块，除非有某个被包含代码块引入了对该名称的不同绑定。

当一个名称在代码块中被使用时，会由包含它的最近作用域来解析。对一个代码块可见的所有这种作用域的集合称为该代码块的环境。

一个作用域是一个 [命名空间](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/16_class/09_namespace.ipynb) 可直接访问的 Python 程序的文本区域。这里的 “可直接访问” 意味着对名称的非限定引用（限定引用指点号表达式例如 math.pi）会尝试在命名空间中查找名称。


```python
# 全局变量作用域为当前模块
a = '全局变量'
def f():
    # print 内置名称作用域包含全局
    print(f'print 函数的命名空间可以访问：{a}')
    return f'f 的命名空间可以访问：{a}'

print(a)
print(f())
```

    全局变量
    print 函数的命名空间可以访问：全局变量
    f 的命名空间可以访问：全局变量
    


```python
# 全局变量作用域为当前模块
# 但被包含命名空间引入了同名的局部变量
a = '全局变量'
def f():
    # f 中定义的局部变量
    # 作用域为函数内部
    a = '局部变量'
    print(f'print 函数的命名空间可以访问：{a}')
    return f'f 的命名空间可以访问：{a}'

print(a)
print(f())
```

    全局变量
    print 函数的命名空间可以访问：局部变量
    f 的命名空间可以访问：局部变量
    

虽然作用域是静态地确定的，但它们会被动态地使用。嵌套作用域的搜索顺序:
- 最先搜索最内部作用域包含的局部名称
- 从最近的封闭作用域开始搜索作用域包含的名称
- 倒数第二个作用域包含当前模块的全局名称
- 最外面的作用域（最后搜索）是包含内置名称的命名空间


```python
# 搜索最内部作用域名称 str
# 屏蔽上层作用域
def f():
    str = 0
    def f1():
        str = 1
        return str
    return f1()

f(), str
```




    (1, str)




```python
# 搜索最近封闭作用域名称 str
# 屏蔽上层作用域
def f():
    str = 0
    def f1():
        return str
    return f1()

f(), str
```




    (0, str)




```python
# 搜索当前模块作用域名称 str
# 屏蔽上层作用域
str = '当前模块str'
def f():
    def f1():
        return str
    return f1()

f()
```




    '当前模块str'




```python
# 搜索最外面作用域名称 str
# 删除前面对 str 的绑定
del str
# 注意，运行多次会将内置名称 str 都删除

def f():
    def f1():
        return str
    return f1()

f()
```




    str



可见，当前模块中的全局名称，最好不要和内置名称相同，它会屏蔽掉内置名称，从而不可以直接使用内置功能。内置名称如下：


```python
import builtins
dir(builtins)
```




    ['ArithmeticError',
     'AssertionError',
     'AttributeError',
     'BaseException',
     'BlockingIOError',
     'BrokenPipeError',
     'BufferError',
     'BytesWarning',
     'ChildProcessError',
     'ConnectionAbortedError',
     'ConnectionError',
     'ConnectionRefusedError',
     'ConnectionResetError',
     'DeprecationWarning',
     'EOFError',
     'Ellipsis',
     'EnvironmentError',
     'Exception',
     'False',
     'FileExistsError',
     'FileNotFoundError',
     'FloatingPointError',
     'FutureWarning',
     'GeneratorExit',
     'IOError',
     'ImportError',
     'ImportWarning',
     'IndentationError',
     'IndexError',
     'InterruptedError',
     'IsADirectoryError',
     'KeyError',
     'KeyboardInterrupt',
     'LookupError',
     'MemoryError',
     'ModuleNotFoundError',
     'NameError',
     'None',
     'NotADirectoryError',
     'NotImplemented',
     'NotImplementedError',
     'OSError',
     'OverflowError',
     'PendingDeprecationWarning',
     'PermissionError',
     'ProcessLookupError',
     'RecursionError',
     'ReferenceError',
     'ResourceWarning',
     'RuntimeError',
     'RuntimeWarning',
     'StopAsyncIteration',
     'StopIteration',
     'SyntaxError',
     'SyntaxWarning',
     'SystemError',
     'SystemExit',
     'TabError',
     'TimeoutError',
     'True',
     'TypeError',
     'UnboundLocalError',
     'UnicodeDecodeError',
     'UnicodeEncodeError',
     'UnicodeError',
     'UnicodeTranslateError',
     'UnicodeWarning',
     'UserWarning',
     'ValueError',
     'Warning',
     'WindowsError',
     'ZeroDivisionError',
     '__IPYTHON__',
     '__build_class__',
     '__debug__',
     '__doc__',
     '__import__',
     '__loader__',
     '__name__',
     '__package__',
     '__spec__',
     'abs',
     'all',
     'any',
     'ascii',
     'bin',
     'bool',
     'breakpoint',
     'bytearray',
     'bytes',
     'callable',
     'chr',
     'classmethod',
     'compile',
     'complex',
     'copyright',
     'credits',
     'delattr',
     'dict',
     'dir',
     'display',
     'divmod',
     'enumerate',
     'eval',
     'exec',
     'filter',
     'float',
     'format',
     'frozenset',
     'get_ipython',
     'getattr',
     'globals',
     'hasattr',
     'hash',
     'help',
     'hex',
     'id',
     'input',
     'int',
     'isinstance',
     'issubclass',
     'iter',
     'len',
     'license',
     'list',
     'locals',
     'map',
     'max',
     'memoryview',
     'min',
     'next',
     'object',
     'oct',
     'open',
     'ord',
     'pow',
     'print',
     'property',
     'range',
     'repr',
     'reversed',
     'round',
     'set',
     'setattr',
     'slice',
     'sorted',
     'staticmethod',
     'str',
     'sum',
     'super',
     'tuple',
     'type',
     'vars',
     'zip']


