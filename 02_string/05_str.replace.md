## str.replace 替换

字符串方法 str.replace()，Python 官方文档描述如下：


```python
help(str.replace)
```

    Help on method_descriptor:
    
    replace(self, old, new, count=-1, /)
        Return a copy with all occurrences of substring old replaced by new.
        
          count
            Maximum number of occurrences to replace.
            -1 (the default value) means replace all occurrences.
        
        If the optional argument count is given, only the first count occurrences are
        replaced.
    
    

返回字符串的副本，其中出现的所有子字符串 old 都将被替换为 new。如果给出了可选参数 count，则只替换前 count 次出现。


```python
'python python'.replace('p','C')
```




    'Cython Cython'




```python
'python python'.replace('py','Cpy',1)
```




    'Cpython python'



如果 old 为空字符串，则在每个字符之间（包括前后）插入 new：


```python
'python python'.replace('','C')
```




    'CpCyCtChCoCnC CpCyCtChCoCnC'



如果 new 为空字符串，则相当于去除了 old：


```python
'python python'.replace('p','')
```




    'ython ython'


