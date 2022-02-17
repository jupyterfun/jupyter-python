## f-string 格式化字符串

f-string 即格式化字符串字面值。字符串以 'f' 或 'F' 为前缀。这种字符串可包含替换字段，即以 {} 标示的表达式。格式化字符串字面值，会在运行时将表达式求值，而其他字符串字面值总是一个常量。

格式化字符串字面值中的表达式会被当作包含在圆括号中的普通 Python 表达式一样处理，但有少数例外。

空表达式不被允许，lambda 和赋值表达式 :=（python 3.8版添加）必须显式地加上圆括号。


```python
f'{(a := 1+1)}' # python 3.8 才能运行
```




    '2'




```python
f'{(lambda x:1)}'
```




    '<function <lambda> at 0x000001D70B06CA60>'



替换表达式可以包含换行（例如在三重引号字符串中），但是不能包含注释。


```python
a = 3; b = 2
f'''3+2\
-5=
{a +
b - 5}'''
```




    '3+2-5=\n0'



每个表达式会在格式化字符串字面值所包含的位置按照从左至右的顺序被求值。


```python
f'{1+2 > 3}'
```




    'False'



可以在表达式后加一个等于号 '='（3.8 新版功能），提供了等于号 '=' 的时候，输出将包含 '='、'=' 前后的空格以及求值结果。默认情况下，'=' 会导致表达式的 repr() 被使用，除非专门指定了格式。


```python
foo = "bar"
f"{ foo = }"
```




    " foo = 'bar'"



可以带一个以叹号 '!' 标示的转换字段，转换符 '!s' 即对结果调用 str()，'!r' 为调用 repr()，而 '!a' 为调用 ascii()。


```python
foo = "bar"
f"{foo = !s}"
```




    'foo = bar'



还可带一个以冒号 ':' 标示的格式说明符，“格式化迷你语言” 与 str.format() 方法所使用的微语言一致，详见 [str.format](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/02_string/25_str.format.ipynb) 方法。


```python
foo = 3.14
f"{foo:.4f}"
```




    '3.1400'




```python
f'{123:#o}'
```




    '0o173'




```python
a=5/6
f'{a:.2%}'
```




    '83.33%'



格式表达式中不允许有反斜杠，这会引发错误:


```python
f"newline: {ord('\n')}"
```


      File "<ipython-input-23-30c78f70325d>", line 1
        f"newline: {ord('\n')}"
        ^
    SyntaxError: f-string expression part cannot include a backslash
    


想包含需要用反斜杠转义的值，可以创建一个临时变量:


```python
newline = ord('\n')
f"newline: {newline}"
```




    'newline: 10'



格式化字符串字面值不可用作文档字符串，即便其中没有包含表达式:


```python
def foo():
    f"Not a docstring"

print(foo.__doc__)
```

    None
    
