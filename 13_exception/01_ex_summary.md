## 错误和异常

异常中断代码块的正常控制流程以便处理 **错误** 或 **其他异常条件** 。它是 Python 中的一类对象。一个异常表示一个或一类错误。

异常会在错误被检测到的位置引发，它可以被 **当前包围发生错误的代码块** 或是 **任何直接或间接调用发生错误的代码块的其他代码块** 所处理。

Python 解析器会在检测到代码运行错误的时候引发异常。也可以通过 raise 语句显式地引发异常。

异常处理通过 [try 语句](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/10_statement/14_try.ipynb) 来指定。该语句的 finally 子句可被用来指定清理代码，它并不处理异常，而是无论之前的代码是否发生异常都会被执行。

Python 的错误处理采用的是 “终止” 模型：异常处理器可以找出发生了什么问题，并在外层继续执行，但它不能修复错误的根源并重试失败的操作（除非通过从顶层重新进入出错的代码片段）。

当一个异常完全未被处理时，解释器会终止程序的执行，或者返回交互模式。无论是哪种情况，它都会打印栈回溯信息，除非是当异常为 SystemExit 的时候。

异常是通过类实例来标识的。except 子句必须引用实例的类或是其所属的基类。实例可通过处理器被接收，并可携带有关异常条件的附加信息。

在 Python 中，所有异常必须为一个派生自 BaseException 的类的实例。

内置异常类可以被子类化以定义新的异常。鼓励从 Exception 类或它的某个子类而不是从 BaseException 来派生新的异常。

内置异常的类层级结构如下：

```
BaseException
+-- SystemExit
+-- KeyboardInterrupt
+-- GeneratorExit
+-- Exception
      +-- StopIteration
      +-- StopAsyncIteration
      +-- ArithmeticError
      | +-- FloatingPointError
      | +-- OverflowError
      | +-- ZeroDivisionError
      +-- AssertionError
      +-- AttributeError
      +-- BufferError
      +-- EOFError
      +-- ImportError
      | +-- ModuleNotFoundError
      +-- LookupError
      | +-- IndexError
      | +-- KeyError
      +-- MemoryError
      +-- NameError
      | +-- UnboundLocalError
      +-- OSError
      | +-- BlockingIOError
      | +-- ChildProcessError
      | +-- ConnectionError
      | | +-- BrokenPipeError
      | | +-- ConnectionAbortedError
      | | +-- ConnectionRefusedError
      | | +-- ConnectionResetError
      | +-- FileExistsError
      | +-- FileNotFoundError
      | +-- InterruptedError
      | +-- IsADirectoryError
      | +-- NotADirectoryError
      | +-- PermissionError
      | +-- ProcessLookupError
      | +-- TimeoutError
      +-- ReferenceError
      +-- RuntimeError
      | +-- NotImplementedError
      | +-- RecursionError
      +-- SyntaxError
      | +-- IndentationError
      | +-- TabError
      +-- SystemError
      +-- TypeError
      +-- ValueError
      | +-- UnicodeError
      | +-- UnicodeDecodeError
      | +-- UnicodeEncodeError
      | +-- UnicodeTranslateError
      +-- Warning
           +-- DeprecationWarning
           +-- PendingDeprecationWarning
           +-- RuntimeWarning
           +-- SyntaxWarning
           +-- UserWarning
           +-- FutureWarning
           +-- ImportWarning
           +-- UnicodeWarning
           +-- BytesWarning
           +-- ResourceWarning
```
