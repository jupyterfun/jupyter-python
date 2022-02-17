## str.format 格式化

字符串方法 str.format()，Python 官方文档描述如下：


```python
help(str.format)
```

    Help on method_descriptor:
    
    format(...)
        S.format(*args, **kwargs) -> str
        
        Return a formatted version of S, using substitutions from args and kwargs.
        The substitutions are identified by braces ('{' and '}').
    
    

执行字符串格式化操作。调用此方法的字符串可以包含字符串字面值或者以花括号 {} 括起来的替换域。每个替换域可以包含一个位置参数的数字索引，或者一个关键字参数的名称。返回的字符串副本中每个替换域都会被替换为对应参数的字符串值。


```python
"The sum of 1 + 2 is {0}".format(1+2)
```




    'The sum of 1 + 2 is 3'



如果你需要在字面文本中包含花括号字符，可以通过重复来转义:


```python
"{{python}}".format()
```




    '{python}'



位置传参和关键字传参方式非常灵活，多个位置索引依次为 0,1,2……，且可以不插入字符串中；关键字传参则需要将关键字插入字符串中：


```python
'{} and {} are both {age} years old.\
'.format('A','B',age=18)
```




    'A and B are both 18 years old.'




```python
'{1} and {0} are both {age} years old.\
'.format('A','B',age=18)
```




    'B and A are both 18 years old.'




```python
'{age} and {} are both {} years old.\
'.format('A','B',age=18)
```




    '18 and A are both B years old.'




```python
'{0} and {0} are both {0} years old.\
'.format('A','B',age=18)
```




    'A and A are both A years old.'



通常，格式化值的工作由值本身的 `__format__()` 方法来完成。但是，在某些情况下最好强制将类型格式化为一个字符串，覆盖其本身的格式化定义。通过在调用 `__format__()` 之前将值转换为字符串，可以绕过正常的格式化逻辑。

目前支持的转换旗标有三种: '!s' 会对值调用 str()，'!r' 调用 repr() 而 '!a' 则调用 ascii()。


```python
'{1!s} and {0!r} are both {age!a} years old.\
'.format('A','B',age=18)
```




    "B and 'A' are both 18 years old."



可以包含值应如何呈现的规格描述，例如字段宽度、对齐、填充、小数精度等细节信息。每种值类型可以定义自己的 “格式化迷你语言” 或解读方式。

### 各种格式化方式示例：


```python
# 复数格式化
('The complex number {0} is formed'
 ' from the real part {0.real} '
 'and the imaginary part {0.imag}.').format(3-5j)
```




    'The complex number (3-5j) is formed from the real part 3.0 and the imaginary part -5.0.'




```python
# 利用索引取出某项格式化，不可切片
'X: {0[0]}; Y: {0[1]}'.format([1,2,3])
```




    'X: 1; Y: 2'




```python
# 切片格式化
a = [1,2,3]
'X: {0}; Y: {1}'.format(a[:2],a[-2:])
```




    'X: [1, 2]; Y: [2, 3]'




```python
# 右对齐
'{:>20}'.format('right aligned')
```




    '       right aligned'




```python
# 填充 ~ 居中
'{:~^20}'.format('centered')
```




    '~~~~~~centered~~~~~~'




```python
# 更复杂的排版
for i, w in zip('<^>', ['left', 'center', 'right']):
    print('{0:{fill}{align}20}'.format(w, fill=i, align=i))
```

    left<<<<<<<<<<<<<<<<
    ^^^^^^^center^^^^^^^
    >>>>>>>>>>>>>>>right
    


```python
# 数字前填充 0
'{:05}'.format(12)
```




    '00012'




```python
# 设置保留精度
'{:f}; {:+.1f}'.format(3.14, -3.14)
```




    '3.140000; -3.1'




```python
# 各种进制格式化
"int: {0:d}; hex: {0:x}; oct: {0:o}; \
bin: {0:b}".format(42)
```




    'int: 42; hex: 2a; oct: 52; bin: 101010'




```python
# 保留进制前缀
"int: {0:d}; hex: {0:#x}; oct: {0:#o}; \
bin: {0:#b}".format(42)
```




    'int: 42; hex: 0x2a; oct: 0o52; bin: 0b101010'




```python
# 让数字更易读
'{:,}'.format(1234567890)
```




    '1,234,567,890'




```python
# 百分比格式化
'Correct answers: {:.2%}'.format(5/6)
```




    'Correct answers: 83.33%'




```python
# 特定类型的专属格式化
import datetime
d = datetime.datetime(2010, 7, 4, 12, 15, 58)
'{:%Y-%m-%d %H:%M:%S}'.format(d)
```




    '2010-07-04 12:15:58'




```python
# IP地址格式化
octets = [192, 168, 0, 1]
'{:02X}{:02X}{:02X}{:02X}'.format(*octets)
```




    'C0A80001'



### “格式化迷你语言” 总结

各种对齐选项的含义：
- '<' 强制字段在可用空间内左对齐（这是大多数对象的默认值）。
- '>' 强制字段在可用空间内右对齐（这是数字的默认值）。
- '=' 强制将填充放置在符号（如果有）之后但在数字之前。这用于以 “+000000120” 形式打印字段。此对齐选项仅对数字类型有效。当 ’0’  紧接在字段宽度之前时，它成为默认值。
- '^' 强制字段在可用空间内居中。

仅对数字类型有效选项：
- '+' 表示标志应该用于正数和负数。
- '-' 表示标志应仅用于负数（这是默认行为）。
- space 表示应在正数上使用前导空格，在负数上使用减号。
- '#' 选项可以让“替代形式”被用于转换。替代形式可针对不同类型分别定义。对于整数类型，当使用二进制、八进制或十六进制输出时，此选项会为输出值添加相应的 '0b', '0o' 或 '0x' 前缀。
- ',' 选项表示使用逗号作为千位分隔符。对于感应区域设置的分隔符，请改用 'n' 整数表示类型。
- '_' 选项表示对浮点表示类型和整数表示类型 'd' 使用下划线作为千位分隔符。对于整数表示类型 'b','o', 'x' 和 'X'，将为每 4 个数位插入一个下划线。对于其他表示类型指定此选项则将导致错误。

确定了数据应如何呈现：
- 's' 字符串格式。这是字符串的默认类型，可以省略。
- 'b' 二进制格式。输出以 2 为基数的数字。
- 'c' 字符。在打印之前将整数转换为相应的 unicode 字符。
- 'd' 十进制整数。输出以 10 为基数的数字。
- 'o' 八进制格式。输出以 8 为基数的数字。
- 'x' 十六进制格式。输出以 16 为基数的数字，使用小写字母表示 9 以上的数码。
- 'X' 十六进制格式。输出以 16 为基数的数字，使用大写字母表示 9 以上的数码。
- 'n' 数字。这与 'd' 相似，不同之处在于它会使用当前区域设置来插入适当的数字分隔字符。
- 'e' 指数表示。以使用字母’e’ 来标示指数的科学计数法打印数字。默认的精度为 6。
- 'E' 指数表示。与 'e' 相似，不同之处在于它使用大写字母’E’ 作为分隔字符。
- 'f' 定点表示。将数字显示为一个定点数。默认的精确度为 6。
- 'F' 定点表示。与 'f' 相似，但会将 nan 转为 NAN 并将 inf 转为 INF。
- 'g' 常规格式。对于给定的精度 p >= 1，这会将数值舍入到 p 位有效数字，再将结果以定点格式或科学计数法进行格式化，具体取决于其值的大小。
- 'G' 常规格式。类似于 'g'，不同之处在于当数值非常大时会切换为 'E'。无穷与 NaN 也会表示为大写形式。
- 'n' 数字。这与 'g' 相似，不同之处在于它会使用当前区域设置来插入适当的数字分隔字符。
- '%' 百分比。将数字乘以 100 并显示为定点 ('f') 格式，后面带一个百分号。

