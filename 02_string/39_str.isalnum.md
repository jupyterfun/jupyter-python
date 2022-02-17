## str.isalnum 是字母或数字？

字符串方法 str.isalnum()，Python 官方文档描述如下：


```python
help(str.isalnum)
```

    Help on method_descriptor:
    
    isalnum(self, /)
        Return True if the string is an alpha-numeric string, False otherwise.
        
        A string is alpha-numeric if all characters in the string are alpha-numeric and
        there is at least one character in the string.
    
    

如果字符串中的所有字符都是字母或数字且至少有一个字符，则返回 True ，否则返回 False 。


```python
''.isalnum()
```




    False




```python
'python123'.isalnum()
```




    True




```python
'python 123'.isalnum()
```




    False




```python
'γ'.isalnum()
```




    True


