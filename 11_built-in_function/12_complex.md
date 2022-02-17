## complex 创建复数

内置函数（类）complex，Python 官方文档描述如下：


```python
help(complex)
```

    Help on class complex in module builtins:
    
    class complex(object)
     |  complex(real=0, imag=0)
     |  
     |  Create a complex number from a real part and an optional imaginary part.
     |  
     |  This is equivalent to (real + imag*1j) where imag defaults to 0.
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
     |  __format__(...)
     |      complex.__format__() -> str
     |      
     |      Convert to a string according to format_spec.
     |  
     |  __ge__(self, value, /)
     |      Return self>=value.
     |  
     |  __getattribute__(self, name, /)
     |      Return getattr(self, name).
     |  
     |  __getnewargs__(...)
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
     |  __rpow__(self, value, mod=None, /)
     |      Return pow(value, self, mod).
     |  
     |  __rsub__(self, value, /)
     |      Return value-self.
     |  
     |  __rtruediv__(self, value, /)
     |      Return value/self.
     |  
     |  __sub__(self, value, /)
     |      Return self-value.
     |  
     |  __truediv__(self, value, /)
     |      Return self/value.
     |  
     |  conjugate(...)
     |      complex.conjugate() -> complex
     |      
     |      Return the complex conjugate of its argument. (3-4j).conjugate() == 3+4j.
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
    
    

返回值为 real + imag*1j 的复数，或将字符串或数字转换为复数。
- 如果第一个形参是字符串，则它被解释为一个复数，并且函数调用时必须没有第二个形参。
- 第二个形参不能是字符串。
- 每个实参都可以是任意的数值类型（包括复数）。
- 如果省略了 imag，则默认值为零，构造函数会像 int 和 float 一样进行数值转换。
- 如果两个实参都省略，则返回 0j。
- 当从字符串转换时，字符串在 + 或 - 的周围必须不能有空格。


```python
type(complex)
```




    type




```python
complex('1')
```




    (1+0j)




```python
complex('1+2j')
```




    (1+2j)




```python
complex(1j, 2j)
```




    (-2+1j)




```python
complex(1j)
```




    1j




```python
complex()
```




    0j




```python
complex('1 + 2j')
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-7-fd0fa4b53d7c> in <module>
    ----> 1 complex('1 + 2j')
    

    ValueError: complex() arg is a malformed string

