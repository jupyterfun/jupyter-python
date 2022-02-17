## hash() 返回对象的哈希值

内置函数 hash()，Python 官方文档描述如下：


```python
help(hash)
```

    Help on built-in function hash in module builtins:
    
    hash(obj, /)
        Return the hash value for the given object.
        
        Two objects that compare equal must also have the same hash value, but the
        reverse is not necessarily true.
    
    

返回对象的哈希值（如果它有的话）。哈希值是整数。它们在集合或字典查找元素时用来快速比较集合的元素或字典的键。相同大小的数字有相同的哈希值。

可哈希对象必须具有相同的哈希值比较结果才会相同。


```python
hash(1) == hash(1.0) == hash(True)
```




    True




```python
1 == 1.0 == True
```




    True




```python
hash('abc')
```




    2812132477407752679




```python
hash((1,2,3))
```




    529344067295497451




```python
hash([1,2,3])
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-5-35e31e935e9e> in <module>
    ----> 1 hash([1,2,3])
    

    TypeError: unhashable type: 'list'



```python
hash((1,2))
```
