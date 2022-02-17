## float 创建浮点数

内置函数（类）float，Python 官方文档描述如下：


```python
help(float)
```

    Help on class float in module builtins:
    
    class float(object)
     |  float(x=0, /)
     |  
     |  Convert a string or number to a floating point number, if possible.
     |  
     |  Methods defined here:
     |  
     |  __abs__(self, /)
     |      abs(self)
     |  
     |  __add__(self, value, /)
     |      Return self+value.
     |  
     |  __bool__(self, /)
     |      self != 0
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
     |  __floordiv__(self, value, /)
     |      Return self//value.
     |  
     |  __format__(self, format_spec, /)
     |      Formats the float according to format_spec.
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
     |  __int__(self, /)
     |      int(self)
     |  
     |  __le__(self, value, /)
     |      Return self<=value.
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
     |  __pos__(self, /)
     |      +self
     |  
     |  __pow__(self, value, mod=None, /)
     |      Return pow(self, value, mod).
     |  
     |  __radd__(self, value, /)
     |      Return value+self.
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
     |  __rmod__(self, value, /)
     |      Return value%self.
     |  
     |  __rmul__(self, value, /)
     |      Return value*self.
     |  
     |  __round__(self, ndigits=None, /)
     |      Return the Integral closest to x, rounding half toward even.
     |      
     |      When an argument is passed, work like built-in round(x, ndigits).
     |  
     |  __rpow__(self, value, mod=None, /)
     |      Return pow(value, self, mod).
     |  
     |  __rsub__(self, value, /)
     |      Return value-self.
     |  
     |  __rtruediv__(self, value, /)
     |      Return value/self.
     |  
     |  __str__(self, /)
     |      Return str(self).
     |  
     |  __sub__(self, value, /)
     |      Return self-value.
     |  
     |  __truediv__(self, value, /)
     |      Return self/value.
     |  
     |  __trunc__(self, /)
     |      Return the Integral closest to x between 0 and x.
     |  
     |  as_integer_ratio(self, /)
     |      Return integer ratio.
     |      
     |      Return a pair of integers, whose ratio is exactly equal to the original float
     |      and with a positive denominator.
     |      
     |      Raise OverflowError on infinities and a ValueError on NaNs.
     |      
     |      >>> (10.0).as_integer_ratio()
     |      (10, 1)
     |      >>> (0.0).as_integer_ratio()
     |      (0, 1)
     |      >>> (-.25).as_integer_ratio()
     |      (-1, 4)
     |  
     |  conjugate(self, /)
     |      Return self, the complex conjugate of any float.
     |  
     |  hex(self, /)
     |      Return a hexadecimal representation of a floating-point number.
     |      
     |      >>> (-0.1).hex()
     |      '-0x1.999999999999ap-4'
     |      >>> 3.14159.hex()
     |      '0x1.921f9f01b866ep+1'
     |  
     |  is_integer(self, /)
     |      Return True if the float is an integer.
     |  
     |  ----------------------------------------------------------------------
     |  Class methods defined here:
     |  
     |  __getformat__(typestr, /) from builtins.type
     |      You probably don't want to use this function.
     |      
     |        typestr
     |          Must be 'double' or 'float'.
     |      
     |      It exists mainly to be used in Python's test suite.
     |      
     |      This function returns whichever of 'unknown', 'IEEE, big-endian' or 'IEEE,
     |      little-endian' best describes the format of floating point numbers used by the
     |      C type named by typestr.
     |  
     |  __set_format__(typestr, fmt, /) from builtins.type
     |      You probably don't want to use this function.
     |      
     |        typestr
     |          Must be 'double' or 'float'.
     |        fmt
     |          Must be one of 'unknown', 'IEEE, big-endian' or 'IEEE, little-endian',
     |          and in addition can only be one of the latter two if it appears to
     |          match the underlying C reality.
     |      
     |      It exists mainly to be used in Python's test suite.
     |      
     |      Override the automatic determination of C-level floating point type.
     |      This affects how floats are converted to and from binary strings.
     |  
     |  fromhex(string, /) from builtins.type
     |      Create a floating-point number from a hexadecimal string.
     |      
     |      >>> float.fromhex('0x1.ffffp10')
     |      2047.984375
     |      >>> float.fromhex('-0x1p-1074')
     |      -5e-324
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
     |  imag
     |      the imaginary part of a complex number
     |  
     |  real
     |      the real part of a complex number
    
    

返回从数字或字符串 x 生成的浮点数。

如果实参是字符串:
- 它必须是包含十进制数字的字符串;
- 通常是 Python 整数或浮点数的字符串形式；
- 也可以是 'NaN'（非数字）、表示正负无穷大的字符串（"Infinity" 或 "inf"）。字母大小写随意；
- 字符串前后可以有空白字符。

如果实参是整数或浮点数，则返回具有相同值（在 Python 浮点精度范围内）的浮点数。如果实参在 Python 浮点精度范围外，则会触发OverflowError。

如果没有实参，则返回 0.0 。


```python
type(float)
```




    type




```python
float()
```




    0.0




```python
float(1)
```




    1.0




```python
float(-  1.0)
```




    -1.0




```python
float(' -1.0 \n')
```




    -1.0




```python
float(' 01_2.1_4 ')
```




    12.14




```python
float('0001')
```




    1.0




```python
float('3.14e02')
```




    314.0




```python
float('-naN')
```




    nan




```python
float('-inf')
```




    -inf


