## str.isprintable 是可打印字符？

字符串方法 str.isprintable()，Python 官方文档描述如下：


```python
help(str.isprintable)
```

    Help on method_descriptor:
    
    isprintable(self, /)
        Return True if the string is printable, False otherwise.
        
        A string is printable if all of its characters are considered printable in
        repr() or if it is empty.
    
    

如果字符串中所有字符均为可打印字符或字符串为空则返回 True，否则返回 False。

不可打印字符是在 Unicode 字符数据库中被定义为 ”Other” 或 ”Separator” 的字符，例外情况是 ASCII 空格字符 (0x20) 被视作可打印字符。

请注意在此语境下可打印字符是指当对一个字符串发起调用 repr() 时不必被转义的字符。它们与字符串写入 sys.stdout 或 sys.stderr 时所需的处理无关。


```python
''.isprintable()
```




    True




```python
' '.isprintable()
```




    True




```python
'\n'.isprintable()
```




    False




```python
'\python'.isprintable()
```




    True




```python
'py\thon'.isprintable()
```




    False


