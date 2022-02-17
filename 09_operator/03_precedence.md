## 操作符优先级

Python 表达式语句中操作符的优先顺序从最低优先级（最后绑定）到最高优先级（最先绑定）如下：

- `:=` 赋值表达式
- `lambda` lambda 表达式
- `if -- else` 条件表达式
- `or` 布尔逻辑或 OR
- `and` 布尔逻辑与 AND
- `not x` 布尔逻辑非 NOT
- `in`, `not in`, `is`, `is not`, `<`, `<=`, `>`, `>=`, `!=`, `==` 比较运算
- `|` 按位或 OR
- `^` 按位异或 XOR
- `&` 按位与 AND
- `<<`, `>>` 移位
- `+`, `-` 加和减
- `*`, `/`, `//`, `%` 乘，矩阵乘，除，整除，取余
- `+x`, `-x`, `~x` 正，负，按位非 NOT
- `**` 乘方（右边的先绑定）
- `await x`  await 表达式
- `x[index]`, `x[index:index]`, `x(arguments...)`, `x.attribute`  抽取，切片，调用，属性引用
- `(expressions...)`, `[expressions...]`, `{key: value...}`, `{expressions...}` 绑定或加圆括号的表达式，列表显示，字典显示，集合显示

一个表达式语句中可以有多个上述操作符，最终返回一个值（包括返回值为 None 的函数调用）。

而赋值语句中的赋值操作符 `=`，`+=`，`-=`，`*=`，`/=`，`//=`，`%=`，`&=`，`|=`，`^=`，`>>=`，`<<=`，`**=`，在操作符中优先级最低，它右边表达式的值计算完之后，才最后绑定到左边的名称。

举例如下：


```python
value = int('2')**(-1) == 2/(3+1)
value
```




    True




```python
int('2')**(-1) == 2/(3+1)
```




    True




```python
[].append(1) is None and not 1 - 1
```




    True




```python
value = 1 if 'a' in 'a b c'.split()[1:3] else 2
value
```




    2




```python
value **= 3 + 2 * 1
value
```




    32



操作符 `=` 可以用来连续赋值：


```python
a = b = c = 1
a,b,c
```




    (1, 1, 1)


