## round() 数字舍入

内置函数 round()，Python 官方文档描述如下：


```python
help(round)
```

    Help on built-in function round in module builtins:
    
    round(number, ndigits=None)
        Round a number to a given precision in decimal digits.
        
        The return value is an integer if ndigits is omitted or None.  Otherwise
        the return value has the same type as the number.  ndigits may be negative.
    
    

返回 number 舍入到小数点后 ndigits 位精度的值。如果 ndigits 被省略或为 None，则返回最接近输入值的整数。

对于支持 round() 的内置类型，值会被舍入到最接近的 10 的负 ndigits 次幂的倍数；如果与两个倍数的距离相等，则选择偶数。

任何整数值都可作为有效的 ndigits (正数、零或负数)。如果 ndigits 被省略或为 None 则返回值将为整数。否则返回值与 number 的类型相同。

由于大多数十进制小数实际上都不能以浮点数精确地表示。返回值可能会不是预期的四舍五入结果。


```python
round(3.14)
```




    3




```python
round(3.14, 3)
```




    3.14




```python
round(3.14, 0)
```




    3.0




```python
round(13.14,-1)
```




    10.0




```python
round(2.5), round(-2.5)
```




    (2, -2)




```python
round(1.5), round(-1.5)
```




    (2, -2)




```python
round(2.675, 2), round(2.665, 2)
```




    (2.67, 2.67)


