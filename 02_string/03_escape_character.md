## 转义字符

转义字符 `\` 本身不被当作字符，如果要表示一个字符 `\`，需要自己将自己转义：


```python
'\\'
```




    '\\'




```python
'\'
```


      File "<ipython-input-2-d44a383620ab>", line 1
        '\'
           ^
    SyntaxError: EOL while scanning string literal
    


上面这一行报错信息是 SyntaxError: EOL while scanning string literal。这是因为 `\'` 表示的是单引号字符 `'`（Literal）—— 是可被输出到屏幕的 `'`，而不是用来标示字符串的那个 `'`—— 别急，无论哪个初学者第一次读到前面的句子都觉得有点莫名其妙…… —— 于是，Python 编译器扫描这个 “字符串” 的时候，还没找到标示字符串末尾的另外一个 `'` 的时候就读到了 EOL（End Of Line）。

如果你想输出这么个字符串，He said, it's fine.，如果用双引号扩起来 `"` 倒没啥问题，但是如果用单引号扩起来就麻烦了，因为编译器会把 it 后面的那个单引号 `'` 当作字符串结尾。


```python
'He said, it's fine.'
```


      File "<ipython-input-3-2bcf2ca6dd95>", line 1
        'He said, it's fine.'
                     ^
    SyntaxError: invalid syntax
    


于是你就得用转义符 `\`：


```python
# 要么你这么写：
print('He said, it\'s fine.')
# 要么你这么写：
print("He said, it's fine.")
# 要么，不管用单引号还是双引号标示字符串，
# 都习惯于用 \' 和 \" 书写属于字符串内部的引号……
"He said, it\'s fine."
```

    He said, it's fine.
    He said, it's fine.
    




    "He said, it's fine."



转义字符 `\` 可与其他字符组合成有特殊含义的字符：

| 转义字符 | 说明                   |
| ----------- | ------------------------ |
| `\(在行尾时)` | 续行符                |
| `\\`          | 反斜杠符号          |
| `\'`          | 单引号                |
| `\"`          | 双引号                |
| `\a`          | 响铃                   |
| `\b`          | 退格                   |
| `\n`          | 换行                   |
| `\v`          | 纵向制表符          |
| `\t`          | 横向制表符          |
| `\r`          | 回车                   |
| `\f`          | 换页                   |
| `\yy`         | 八进制数 yy 码位的字符 |
| `\xyy`        | 十六进制数 yy 码位的字符 |

续航符，可以将两行代码（或字符串）连接起来，表示一行：


```python
for i in \
range(3): # 两行相当于 for i in range(10):
    print(i)
```

    0
    1
    2
    


```python
'hello \
world'
```




    'hello world'



八进制和十六进制字符举例：


```python
# 八进制字符
'\101', '\102'
```




    ('A', 'B')




```python
# 十六进制字符
'\x41', '\x42'
```




    ('A', 'B')




```python
# 十进制
chr(65),chr(66)
```




    ('A', 'B')



在正则表达式中，转义字符 `\` 的应用更加普遍。详情请看[《正则指引》](https://xue.cn/hub/app/books/21)。
