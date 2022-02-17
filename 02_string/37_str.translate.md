## str.translate 按表转换

文档描述如下：


```python
help(str.translate)
```

    Help on method_descriptor:
    
    translate(self, table, /)
        Replace each character in the string using the given translation table.
        
          table
            Translation table, which must be a mapping of Unicode ordinals to
            Unicode ordinals, strings, or None.
        
        The table must implement lookup/indexing via __getitem__, for instance a
        dictionary or list.  If this operation raises LookupError, the character is
        left untouched.  Characters mapped to None are deleted.
    
    

返回原字符串的副本，其中每个字符按给定的转换表进行映射。转换表必须是一个使用 `__getitem__()` 来实现索引操作的对象，通常为 mapping 或 sequence。当以 Unicode 码位序号（整数）为索引时，转换表对象可以做以下任何一种操作：返回 Unicode 序号或字符串，将字符映射为一个或多个字符；返回 None，将字符从结果字符串中删除；或引发 LookupError 异常，将字符映射为其自身。


```python
ord('p'),ord('C')
```




    (112, 67)




```python
'python'.translate({112:67})
```




    'Cython'




```python
'python'.translate({112:'Cp'})
```




    'Cpython'




```python
'python'.translate({112:None})
```




    'ython'



你可以使用 str.maketrans() 基于不同格式的字符到字符映射来创建一个转换映射表。


```python
table = str.maketrans('pto','123')
'python'.translate(table)
```




    '1y2h3n'


