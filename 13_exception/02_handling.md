## 处理异常

异常处理通过 try 语句（详细语法及使用规则见 [try 语句](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/10_statement/14_try.ipynb)）来实现。

通过 try 语句处理程序已经出现或可能出现异常，使代码能够继续执行，否则异常未被处理，程序终止执行。

例如下列代码要求用户输入有效的整数：


```python
while True:
    try:
        x = int(input("Please enter a number: "))
        break
    except ValueError:
        print("Oops! That was no valid number. Try again...")
```

    Please enter a number:  3.14
    

    Oops! That was no valid number. Try again...
    

    Please enter a number:  314
    

try 语句的工作原理如下：
- 首先执行 try 子句；

- 如果没有异常发生，则跳过 except 子句并完成 try 语句的执行；

- 如果在执行 try 子句时发生了异常，则跳过该子句中剩下的部分。然后，如果异常的类型和 except 关键字后面的异常匹配，则执行 except 子句，然后继续执行 try 语句之后的代码；

- 如果发生的异常和 except 子句中指定的异常不匹配，则将其传递到外部的 try 语句中；如果没有找到处理程序，则它是一个未处理异常，执行将停止并显示异常信息。

一个 try 语句可能有多个 except 子句，以指定不同异常的处理程序，但最多会执行一个处理程序。

处理程序只处理相应的 try 子句中发生的异常。如果发生的异常和 except 子句中的类是同一个类或者是它的基类，则异常和 except 子句中的类是兼容的。如果首先处理了基类，子类不再被处理（子类也被基类处理了）：


```python
class B(Exception):
    pass

class C(B):
    pass

class D(C):
    pass

for cls in [B, C, D]:
    try:
        raise cls()
    except D:
        print("D")
    except C:
        print("C")
    except B:
        print("B")
```

    B
    C
    D
    


```python
class B(Exception):
    pass

class C(B):
    pass

class D(C):
    pass

for cls in [B, C, D]:
    try:
        raise cls()
    except B: # 下列都是 B 的子类，不再被处理
        print("B")
    except C:
        print("C")
    except D:
        print("D")
```

    B
    B
    B
    

最后的 except 子句可以省略异常名，以用作通配符。但请谨慎使用，因为以这种方式很容易掩盖真正的编程错误！它还可用于打印错误消息，然后重新引发异常:


```python
import sys

try:
    3/0
except ValueError as v:
    print(v)
except:
    print("Unexpected error:", sys.exc_info()[0])
    raise
```

    Unexpected error: <class 'ZeroDivisionError'>
    


    ---------------------------------------------------------------------------

    ZeroDivisionError                         Traceback (most recent call last)

    <ipython-input-13-f0b3e840c5ab> in <module>
          2 
          3 try:
    ----> 4     3/0
          5 except ValueError as v:
          6     print(v)
    

    ZeroDivisionError: division by zero


可选的 else 子句，在使用时必须放在所有的 except 子句后面。对于在 try 子句不引发异常时必须执行的代码来说很有用：


```python
try:
    f = open('../11_built-in_function/test.txt',
             'r',encoding='utf-8')
except OSError:
    print('cannot open')
else:
    print(len(f.readlines()), 'lines')
    f.close()
```

    3 lines
    

异常处理程序不仅处理 try 子句中遇到的异常，还处理 try 子句中调用（即使是间接地）的函数内部发生的异常。

如果 try 子句中有多个可能的异常，只处理最先引发的：


```python
def f():
    return 3/0

try:
    f() * int('a')
except ValueError as v:
    print(v)
except  ZeroDivisionError as z:
    print(z)
```

    division by zero
    
