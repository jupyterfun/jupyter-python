## 字符串概述

Python 中处理文本数据使用 str 类型对象，也称为字符串。


```python
type('abc')
```




    str



字符串是由 Unicode 码位构成的不可变序列。每个字符的 Unicode 码位可由内建函数 ord() 查看：


```python
ord('a'), ord('b'), ord('c')
```




    (97, 98, 99)



内建函数 [str()](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/11_built-in_function/59_str.ipynb) 可将其他类型对象转换为字符串：


```python
str(3.14)
```




    '3.14'



字符串有多种不同写法：

- 单引号标示

单引号标示法，如果字符串中有单引号，需要用 `\'` 表示：


```python
'it\'s a book'
```




    "it's a book"



- 双引号标示

双引号标示法，如果字符串中有双引号，需要用 `\"` 表示：


```python
"it's a \"book\""
```




    'it\'s a "book"'



- 三重引号标示

三重引号标示法，可以是三重单引号 `'''`，也可以是三重双引号 `"""`，字符串中的单引号或双引号不受影响，但不能紧挨着：


```python
# 注意最后四个双引号中有一个空格
'''it's a book''', \
"""it's a "book" """ 
```




    ("it's a book", 'it\'s a "book" ')



三重引号标示的字符串可以换行，自动以 `\n` 表示：


```python
'''
it's a 
book
'''
```




    "\nit's a \nbook\n"



若不想引入 `\n`，可以使用续航符 `\`：


```python
'''\
it's a \
book\
'''
```




    "it's a book"



字符串可带前缀 u（或 U），r（或 R），f（或 F）。

u 表示 Unicode 编码字符串（默认，可省略）；r 表示原始字符串，其中的反斜杠会被当作其本身来处理；f 表示[格式化字符串字面值](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/02_string/27_f-string.ipynb)。r 和 f 可连用。


```python
'a\nb{1+1}'
```




    'a\nb{1+1}'




```python
r'a\nb{1+1}'
```




    'a\\nb{1+1}'




```python
f'a\nb{1+1}'
```




    'a\nb2'




```python
rf'a\nb{1+1}'
```




    'a\\nb2'



注意带前缀 b（或 B），表示字节串对象：


```python
type(b'abc')
```




    bytes



字符串是不可变序列，下列切片操作得到的是原来的字符串：


```python
a = 'abc'
b = a[:]
a is b
```




    True


