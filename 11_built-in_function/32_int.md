## int 创建整数

内置函数（类）int，Python 官方文档描述如下：


```python
help(int)
```

    Help on class int in module builtins:
    
    class int(object)
     |  int([x]) -> integer
     |  int(x, base=10) -> integer
     |  
     |  Convert a number or string to an integer, or return 0 if no arguments
     |  are given.  If x is a number, return x.__int__().  For floating point
     |  numbers, this truncates towards zero.
     |  
     |  If x is not a number or if base is given, then x must be a string,
     |  bytes, or bytearray instance representing an integer literal in the
     |  given base.  The literal can be preceded by '+' or '-' and be surrounded
     |  by whitespace.  The base defaults to 10.  Valid bases are 0 and 2-36.
     |  Base 0 means to interpret the base from the string as an integer literal.
     |  >>> int('0b100', base=0)
     |  4
     |  
     |  Built-in subclasses:
     |      bool
     |  
     |  Methods defined here:
     |  
     |  __abs__(self, /)
     |      abs(self)
     |  
     |  __add__(self, value, /)
     |      Return self+value.
     |  
     |  __and__(self, value, /)
     |      Return self&value.
     |  
     |  __bool__(self, /)
     |      self != 0
     |  
     |  __ceil__(...)
     |      Ceiling of an Integral returns itself.
     |  
     |  __divmod__(self, value, /)
     |      Return divmod(self, value).
     |  
     |  __eq__(self, value, /)
     |      Return self==value.
     |  
     |  __float__(self, /)
     |      float(self)
     |  
     |  __floor__(...)
     |      Flooring an Integral returns itself.
     |  
     |  __floordiv__(self, value, /)
     |      Return self//value.
     |  
     |  __format__(self, format_spec, /)
     |      Default object formatter.
     |  
     |  __ge__(self, value, /)
     |      Return self>=value.
     |  
     |  __getattribute__(self, name, /)
     |      Return getattr(self, name).
     |  
     |  __getnewargs__(self, /)
     |  
     |  __gt__(self, value, /)
     |      Return self>value.
     |  
     |  __hash__(self, /)
     |      Return hash(self).
     |  
     |  __index__(self, /)
     |      Return self converted to an integer, if self is suitable for use as an index into a list.
     |  
     |  __int__(self, /)
     |      int(self)
     |  
     |  __invert__(self, /)
     |      ~self
     |  
     |  __le__(self, value, /)
     |      Return self<=value.
     |  
     |  __lshift__(self, value, /)
     |      Return self<<value.
     |  
     |  __lt__(self, value, /)
     |      Return self<value.
     |  
     |  __mod__(self, value, /)
     |      Return self%value.
     |  
     |  __mul__(self, value, /)
     |      Return self*value.
     |  
     |  __ne__(self, value, /)
     |      Return self!=value.
     |  
     |  __neg__(self, /)
     |      -self
     |  
     |  __or__(self, value, /)
     |      Return self|value.
     |  
     |  __pos__(self, /)
     |      +self
     |  
     |  __pow__(self, value, mod=None, /)
     |      Return pow(self, value, mod).
     |  
     |  __radd__(self, value, /)
     |      Return value+self.
     |  
     |  __rand__(self, value, /)
     |      Return value&self.
     |  
     |  __rdivmod__(self, value, /)
     |      Return divmod(value, self).
     |  
     |  __repr__(self, /)
     |      Return repr(self).
     |  
     |  __rfloordiv__(self, value, /)
     |      Return value//self.
     |  
     |  __rlshift__(self, value, /)
     |      Return value<<self.
     |  
     |  __rmod__(self, value, /)
     |      Return value%self.
     |  
     |  __rmul__(self, value, /)
     |      Return value*self.
     |  
     |  __ror__(self, value, /)
     |      Return value|self.
     |  
     |  __round__(...)
     |      Rounding an Integral returns itself.
     |      Rounding with an ndigits argument also returns an integer.
     |  
     |  __rpow__(self, value, mod=None, /)
     |      Return pow(value, self, mod).
     |  
     |  __rrshift__(self, value, /)
     |      Return value>>self.
     |  
     |  __rshift__(self, value, /)
     |      Return self>>value.
     |  
     |  __rsub__(self, value, /)
     |      Return value-self.
     |  
     |  __rtruediv__(self, value, /)
     |      Return value/self.
     |  
     |  __rxor__(self, value, /)
     |      Return value^self.
     |  
     |  __sizeof__(self, /)
     |      Returns size in memory, in bytes.
     |  
     |  __sub__(self, value, /)
     |      Return self-value.
     |  
     |  __truediv__(self, value, /)
     |      Return self/value.
     |  
     |  __trunc__(...)
     |      Truncating an Integral returns itself.
     |  
     |  __xor__(self, value, /)
     |      Return self^value.
     |  
     |  as_integer_ratio(self, /)
     |      Return integer ratio.
     |      
     |      Return a pair of integers, whose ratio is exactly equal to the original int
     |      and with a positive denominator.
     |      
     |      >>> (10).as_integer_ratio()
     |      (10, 1)
     |      >>> (-10).as_integer_ratio()
     |      (-10, 1)
     |      >>> (0).as_integer_ratio()
     |      (0, 1)
     |  
     |  bit_length(self, /)
     |      Number of bits necessary to represent self in binary.
     |      
     |      >>> bin(37)
     |      '0b100101'
     |      >>> (37).bit_length()
     |      6
     |  
     |  conjugate(...)
     |      Returns self, the complex conjugate of any int.
     |  
     |  to_bytes(self, /, length, byteorder, *, signed=False)
     |      Return an array of bytes representing an integer.
     |      
     |      length
     |        Length of bytes object to use.  An OverflowError is raised if the
     |        integer is not representable with the given number of bytes.
     |      byteorder
     |        The byte order used to represent the integer.  If byteorder is 'big',
     |        the most significant byte is at the beginning of the byte array.  If
     |        byteorder is 'little', the most significant byte is at the end of the
     |        byte array.  To request the native byte order of the host system, use
     |        `sys.byteorder' as the byte order value.
     |      signed
     |        Determines whether two's complement is used to represent the integer.
     |        If signed is False and a negative integer is given, an OverflowError
     |        is raised.
     |  
     |  ----------------------------------------------------------------------
     |  Class methods defined here:
     |  
     |  from_bytes(bytes, byteorder, *, signed=False) from builtins.type
     |      Return the integer represented by the given array of bytes.
     |      
     |      bytes
     |        Holds the array of bytes to convert.  The argument must either
     |        support the buffer protocol or be an iterable object producing bytes.
     |        Bytes and bytearray are examples of built-in objects that support the
     |        buffer protocol.
     |      byteorder
     |        The byte order used to represent the integer.  If byteorder is 'big',
     |        the most significant byte is at the beginning of the byte array.  If
     |        byteorder is 'little', the most significant byte is at the end of the
     |        byte array.  To request the native byte order of the host system, use
     |        `sys.byteorder' as the byte order value.
     |      signed
     |        Indicates whether two's complement is used to represent the integer.
     |  
     |  ----------------------------------------------------------------------
     |  Static methods defined here:
     |  
     |  __new__(*args, **kwargs) from builtins.type
     |      Create and return a new object.  See help(type) for accurate signature.
     |  
     |  ----------------------------------------------------------------------
     |  Data descriptors defined here:
     |  
     |  denominator
     |      the denominator of a rational number in lowest terms
     |  
     |  imag
     |      the imaginary part of a complex number
     |  
     |  numerator
     |      the numerator of a rational number in lowest terms
     |  
     |  real
     |      the real part of a complex number
    
    

将一个数字，字符串或字节串转换为整数。参数说明：
- 不给参数返回整数 0。
- 参数 x 为数字时，不能有参数 base，且数字不能是复数。浮点数将取整。
- 参数 x 为字符串或字节串，参数 base 可选，默认按十进制转换，否则按照 base 指定进制转换。
- base 取值范围为 0 和 2~36。
- base 取 0 将按照参数 x 的字面量来精确解释。取其他数字则需符合相应进制规则。
- 字符串或字节串不能是浮点数形式；前面可以有正负号；前后可以有空格，中间则不能有空格。


```python
type(int)
```




    type




```python
int()
```




    0




```python
int(3.18e01), int(10), int(0x10)
```




    (31, 10, 16)




```python
int(' -10 '), int(b' +10')
```




    (-10, 10)




```python
int('10',2), int('10',8), int('z',36)
```




    (2, 8, 35)




```python
int('001'), int('0b10',0)
```




    (1, 2)




```python
int('001',0) # 001 不是合法的整数
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-12-1cf9048a8c3e> in <module>
    ----> 1 int('001',0)
    

    ValueError: invalid literal for int() with base 0: '001'



```python
int('9', 8) # 8 进制没有 9
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-13-3558097bd025> in <module>
    ----> 1 int('9', 8)
    

    ValueError: invalid literal for int() with base 8: '9'



```python
int('3.14') # 不能是浮点数形式
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-14-1456603af047> in <module>
    ----> 1 int('3.14')
    

    ValueError: invalid literal for int() with base 10: '3.14'

