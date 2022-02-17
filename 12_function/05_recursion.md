## 递归函数

函数 return 语句的表达式中包含函数自身的调用，则称该函数为递归函数。

递归函数必须设定退出条件，并且调用过程能够逐步达到退出条件，否则将引发 RecursionError。

例如定义一个计算阶乘的函数：

上述函数的退出条件是 `x == 0`，并且 return 语句中函数调用的参数是 `x-1`，第一层调用函数的参数 `x` 为 5，return 语句进入第二层调用，就变成了 `x-1` 为 4，依此类推，最终以 0 调用函数，达到了退出条件，但是值还没有最终返回，以退出条件下的返回值层层向上返回，最终得到结果。详情查看 [递归函数](https://xue.cn/hub/reader?bookId=1&path=the-craft-of-selfteaching/Part.2.D.4-recursion.ipynb)。


```python
def f(x):
    if x == 0:
        return 1
    else:
        return f(x-1)*x
f(5)
```




    120


