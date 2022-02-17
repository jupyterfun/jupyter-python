## str.join 拼接字符串

字符串方法 str.join()，Python 官方文档描述如下：


```python
help(str.join)
```

    Help on method_descriptor:
    
    join(self, iterable, /)
        Concatenate any number of strings.
        
        The string whose method is called is inserted in between each given string.
        The result is returned as a new string.
        
        Example: '.'.join(['ab', 'pq', 'rs']) -> 'ab.pq.rs'
    
    

返回一个由 iterable 中的字符串拼接而成的字符串。如果 iterable 中存在任何非字符串值则会引发 TypeError。调用该方法的字符串将作为元素之间的分隔。


```python
'~'.join('abc')
```




    'a~b~c'




```python
'acb'.join(['1','2'])
```




    '1acb2'




```python
''.join(['1','2'])
```




    '12'




```python
'-'.join({'1':1,'2':2})
```




    '1-2'




```python
'-'.join(['1',2])
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-9-fc346e5ca62e> in <module>
    ----> 1 '-'.join(['1',2])
    

    TypeError: sequence item 1: expected str instance, int found



```python
'-'.join(b'abc')
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-8-9d04d7060926> in <module>
    ----> 1 '-'.join(b'abc')
    

    TypeError: sequence item 0: expected str instance, int found

