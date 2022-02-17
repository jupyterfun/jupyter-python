## divmod() 求两个数的商和余

内置函数 divmod()，Python 官方文档描述如下：


```python
help(divmod)
```

    Help on built-in function divmod in module builtins:
    
    divmod(x, y, /)
        Return the tuple (x//y, x%y).  Invariant: div*y + mod == x.
    
    

它将两个（非复数）数字作为实参，返回两个数字的（商,余数）元组。对于混合操作数类型，适用二元算术运算符的规则。


```python
divmod(1,2)
```




    (0, 1)




```python
divmod(3.14, 2)
```




    (1.0, 1.1400000000000001)


