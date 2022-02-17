## 生成器函数

函数定义中使用了 [yield 语句](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/10_statement/12_yield.ipynb)，该定义创建的函数是生成器函数。生成器函数通常也直接叫生成器。

当一个生成器函数被调用的时候，它返回一个迭代器，也称为生成器（全称是生成器迭代器，下面所说生成器均指生成器迭代器）。然后通过这个生成器来控制生成器函数的执行。

生成器是一个迭代器，也是一个可迭代对象。但一个生成器生成的 “元素” 只能被使用一次，原因如下：

- 迭代生成器的时候，生成器函数开始执行，执行到 yield，然后执行被挂起，给生成器的调用者返回 yield 之后的表达式的值。挂起后，所有局部状态都被保留下来，包括局部变量的当前绑定，指令指针，内部求值栈和任何异常处理的状态。

- 继续迭代生成器，生成器函数从挂起状态继续执行，执行到 yield，然后执行又被挂起，给生成器的调用者返回 yield 之后的表达式的值。

- 生成器迭代完成时，引发 StopIteration。

在一个生成器函数中，return 语句表示生成器已完成并将导致 StopIteration 被引发。返回值（如果有的话）会被当作一个参数用来构建 StopIteration 并成为 StopIteration.value 属性。


```python
next(g)
```




    0




```python
def f(n):
    yield n
g = f(0)
print(f)
print(g)
```

    <function f at 0x000002480120ACA0>
    <generator object f at 0x000002480122E040>
    


```python
next(g) # 迭代结束
```


    ---------------------------------------------------------------------------

    StopIteration                             Traceback (most recent call last)

    <ipython-input-3-c91425ed1388> in <module>
    ----> 1 next(g) # 迭代结束
    

    StopIteration: 



```python
def f(n):
    yield n
    n += 1
    yield n
    n += 1
    yield n
    # 生成器已完成，后面的不被执行
    return 'end'
    n += 1
    yield n
    
g = f(0)

while True:
    try:
        print(next(g))
    except StopIteration as s:
        print(s.value) # StopIteration.value 属性
        break
# 迭代结束，不能再次迭代生成器
next(g)
```

    0
    1
    2
    end
    


    ---------------------------------------------------------------------------

    StopIteration                             Traceback (most recent call last)

    <ipython-input-10-3ebb4e469fc1> in <module>
         19         break
         20 # 迭代结束，不能再次迭代生成器
    ---> 21 next(g)
    

    StopIteration: 


`yield from` 将可迭代对象中的每一项作为生成器的迭代项：


```python
def f(*args):
    yield from args

g = f(1,2,3)
next(g),list(g)
```




    (1, [2, 3])




```python
def f(arg):
    yield from arg

g = f('123')
print(list(g))
# g 使用结束，再次使用什么也没有，创建了一个空列表
print(list(g))
# 如要再次使用可再创建一个生成器
list(f('123'))
```

    ['1', '2', '3']
    []
    




    ['1', '2', '3']


