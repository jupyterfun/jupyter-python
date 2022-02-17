## format() 格式化

内置函数 format()，Python 官方文档描述如下：


```python
help(format)
```

    Help on built-in function format in module builtins:
    
    format(value, format_spec='', /)
        Return value.__format__(format_spec)
        
        format_spec defaults to the empty string.
        See the Format Specification Mini-Language section of help('FORMATTING') for
        details.
    
    

将 value 转换为 format_spec 控制的 “格式化” 表示。format_spec 的解释取决于 value 实参的类型，但是大多数内置类型使用标准格式化语法：格式化迷你语言。详见 [str.format 格式化](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/02_string/25_str.format.ipynb)。

默认的 format_spec 是一个空字符串，它通常和调用 str(value) 的结果相同。


```python
format('嗨','>10')
```




    '         嗨'




```python
format('嗨','~^10')
```




    '~~~~嗨~~~~~'




```python
format(1,'05')
```




    '00001'




```python
format(3.14,'.3f')
```




    '3.140'




```python
format(123456789,'_')
```




    '123_456_789'




```python
format(123456789,'.2e')
```




    '1.23e+08'




```python
format(123456789)
```




    '123456789'


