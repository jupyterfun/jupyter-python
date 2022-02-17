## pow() 幂运算并取余

内置函数 pow()，Python 官方文档描述如下：


```python
help(pow)
```

    Help on built-in function pow in module builtins:
    
    pow(base, exp, mod=None)
        Equivalent to base**exp with 2 arguments or base**exp % mod with 3 arguments
        
        Some types, such as ints, are able to use a more efficient algorithm when
        invoked using the three argument form.
    
    

返回 base 的 exp 次幂；如果 mod 存在，则返回 base 的 exp 次幂对 mod 取余（比 `pow(base, exp) % mod` 更高效）。

对于混用的操作数类型，则将应用双目算术运算符的类型强制转换规则。
对于 int 操作数，结果具有与操作数相同的类型（强制转换后），除非第二个参数为负值；在这种情况下，所有参数将被转换为浮点数并输出浮点数结果。

对于 int 操作数 base 和 exp，如果给出 mod，则 mod 必须为整数类型并且 mod 必须不为零。如果给出 mod 并且 exp 为负值，则 base 必须相对于 mod 不可整除。在这种情况下，将会返回 `pow(inv_base, -exp, mod)`，其中 inv_base 为 base 的倒数对 mod 取余。

在 3.8 版更改: 对于 int 操作数，三参数形式的 pow 现在允许第二个参数为负值，即可以计算倒数的余数；允许关键字参数。


```python
pow(2, 3, 4)
```




    0




```python
pow(2.0, 3)
```




    8.0




```python
pow(2, -1)
```




    0.5




```python
pow(38, -1, 97) #  38 的倒数对 97 取余为 23
```




    23




```python
23 * 38 % 97 == 1
```




    True




```python
pow(38, -2, 97), pow(23, 2, 97)
```




    (44, 44)


