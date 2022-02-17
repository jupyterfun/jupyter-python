## class 定义类

class 语句用来定义类，语法如下：
```
@assignment_expression
class classname(argument_list):
    suite
```

其中的装饰器 `@assignment_expression`，基类参数及圆括号 `(argument_list)` 是可选项。

类定义是一条可执行语句。它执行时会将类名称 classname 绑定到一个新建的类对象。

没有继承基类参数 argument_list 的类默认继承自基类 object。下列是一个必选参数定义的类，默认继承自 object:


```python
# 创建一个类名为 A 的类
class A: pass

A.__bases__ # 查看基类
```




    (object,)




```python
# 创建一个类 B 继承自 int 和 A
class B(int, A):
    pass

B.__bases__
```




    (int, __main__.A)



类也可以被装饰，就像装饰函数一样，装饰器表达式的求值规则与函数装饰器相同（详见 [def 定义函数](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/10_statement/10_def.ipynb)）。结果随后会被绑定到类名称。


```python
@str
@type
class C: pass

C
```




    "<class 'type'>"



大致相当于：


```python
class C: pass
C = str(type(C))
C
```




    "<class 'type'>"


