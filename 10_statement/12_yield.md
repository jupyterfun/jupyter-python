## yield 语句

yield 语句，仅在定义 [生成器函数](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/12_function/09_generator.ipynb) 时使用，并且仅被用于生成器函数的函数体内部。语法如下：
```
yield from expression
```

`from` 和表达式 `expression` 是可选的，没有表达式默认是 None。

yield 语句整体也是一个可被求值的表达式语句，初始值也是默认 None，可通过 send 方法设置 yield 表达式的值。

在函数定义中使用 yield 使得该定义创建的是生成器函数而非普通函数。当一个生成器函数被调用的时候，它返回一个生成器迭代器。

yield from 相当于将一个可迭代对象 “拆包”，然后逐项被生成器迭代时使用。


```python
# 创建一个简单的生成器函数
def f():
    yield
    
print(f)
# 调用它获得一个生成器
print(f())
# next() 函数迭代生成器获取表达式的值
print(next(f()))
```

    <function f at 0x00000157028A9598>
    <generator object f at 0x000001570286CB88>
    None
    


```python
# 获取并设置 yield 语句的值
def f(n):
    x = yield n
    print(x)
    
g = f(1)
print(next(g))
# 迭代结束，打印出 yield 语句 x 的初始值为 None
print(next(g,'end'))
```

    1
    None
    end
    


```python
# 可通过 send 方法设置当前 yield 表达式的值
# 并返回生成器产生的下一个值
def f(n):
    x = yield n
    print(f'yield 表达式的值为:{x}')
    n += 1
    yield n
    
g = f(0)
next(g), g.send(10)
```

    yield 表达式的值为:10
    




    (0, 1)




```python
def f(*args):
    yield from args

g = f(1,2,3)
next(g),next(g),next(g),next(g,'end')
```




    (1, 2, 3, 'end')




```python
def f(arg):
    yield from arg

g = f('123')
next(g),next(g),next(g),next(g,'end')
```




    ('1', '2', '3', 'end')


