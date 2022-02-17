## 自定义异常

可以通过创建新的异常类来自定义代码执行错误引发的异常。许多标准模块定义了它们自己的异常，以报告它们定义的函数中可能出现的错误。

异常通常应该直接或间接地从 Exception 类派生。定义的异常类，可以执行任何其他类可以执行的任何操作，但通常保持简单，只提供一些属性，这
些属性允许处理程序为异常提取有关错误的信息。

在创建可能引发多个不同错误的模块时，通常的做法是为该模块定义的异常创建基类，并为不同错误条件创建特定异常类的子类。大多数异常都定义为名称以 `Error` 结尾，类似于标准异常的命名:


```python
class Error(Exception):
    """Base class for exceptions in this module."""
    pass

class InputError(Error):
    """Exception raised for errors in the input.
    
    Attributes:
        expression -- input expression in which the error occurred
        message -- explanation of the error
    """
    
    def __init__(self, expression, message):
        self.expression = expression
        self.message = message
    
class TransitionError(Error):
    """Raised when an operation attempts a state transition that's not allowed.
    
    Attributes:
        previous -- state at beginning of transition
        next -- attempted new state
        message -- explanation of why the specific transition is not allowed
    """
    
    def __init__(self, previous, next, message):
        self.previous = previous
        self.next = next
        self.message = message
        
raise InputError(3/1,'分母不能为 1')
```


    ---------------------------------------------------------------------------

    InputError                                Traceback (most recent call last)

    <ipython-input-2-d0c6938bc1c4> in <module>
         29         self.message = message
         30 
    ---> 31 raise InputError(3/1,'分母不能为 1')
    

    InputError: (3.0, '分母不能为 1')

