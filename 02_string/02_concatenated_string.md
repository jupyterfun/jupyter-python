## 字符串拼接

### 空格拼接

相邻的两个字符串，无论中间隔了多少个空格（包括 0 个），都会自动连接到一起：


```python
'Py''thon', 'Py'    'thon'
```




    ('Python', 'Python')



甚至可以用 () 包围实现换行拼接，这在字符串（或正则表达式）很长时非常有用：


```python
('Py'
f'thon{3}'
r'\Go')
```




    'Python3\\Go'



### 运算符 `+` 拼接

运算符 `+` 拼接字符串，和空格类似，但 `+` 拼接字符串可以是变量的形式：


```python
a = 'Py'
b = 'thon'
'Py' + b, a + b
```




    ('Python', 'Python')



运算符 `+` 还可以和赋值运算符 `=` 连用，拼接字符串的同时进行赋值：


```python
# 将 a 和 b 拼接，赋值给 a
a += b
print(a)
# 将 b 和 a 拼接，赋值给 b
b += a
b
```

    Python
    




    'thonPython'


