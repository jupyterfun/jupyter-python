## str.format_map 格式化

字符串方法 str.format_map()，Python 官方文档描述如下：


```python
help(str.format_map)
```

    Help on method_descriptor:
    
    format_map(...)
        S.format_map(mapping) -> str
        
        Return a formatted version of S, using substitutions from mapping.
        The substitutions are identified by braces ('{' and '}').
    
    

类似于 str.format(**mapping)，不同之处在于 mapping 会被直接使用。适宜使用此方法的一个例子是当 mapping 为 dict 的子类的情况：


```python
# 创建一个字典子类型，当 键值对 不存在时，返回键
class Default(dict):
    def __missing__(self, key):
        return key
d = Default(a=1)
d['a'], d['b']
```




    (1, 'b')




```python
# country 键值对不存在，所以直接格式化键 ‘country’
'{name} was born in {country}'.format_map(
    Default(name='Guido'))
```




    'Guido was born in country'



与 format 格式化对比：


```python
'{a} is {age}'.format_map({'a':'A', 'age':18})
```




    'A is 18'




```python
'{a} is {age}'.format(**{'a':'A', 'age':18})
```




    'A is 18'


