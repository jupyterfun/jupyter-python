## str.isalpha 是字母（包括汉字等）？

字符串方法 str.isalpha()，Python 官方文档描述如下：


```python
help(str.isalpha)
```

    Help on method_descriptor:
    
    isalpha(self, /)
        Return True if the string is an alphabetic string, False otherwise.
        
        A string is alphabetic if all characters in the string are alphabetic and there
        is at least one character in the string.
    
    

如果字符串中的所有字符都是字母，并且至少有一个字符，返回 True ，否则返回 False 。

字母字符是指那些在 Unicode 字符数据库中定义为 ”Letter” 的字符，即那些具有 ”Lm”、”Lt”、”Lu”、”Ll” 或 ”Lo” 之一的通用类别属性的字符。注意，这与 Unicode 标准中定义的 ”字母” 属性不同。

此处的字母包括汉字等。


```python
''.isalpha()
```




    False




```python
'γ'.isalpha()
```




    True




```python
'嗨你好'.isalpha()
```




    True




```python
'嗨！你好'.isalpha()
```




    False


