## with 语句

with 语句用于包装代码块的执行，代码块带有使用上下文管理器定义的函数或方法。语法如下：
```
with expression as target, expression as target, ...:
    suite
```

带有一个表达式 expression 的 with 语句的执行过程如下:
1. 对上下文表达式求值以获得一个上下文管理器。
2. 载入上下文管理器的 `__enter__()` 以便后续使用。
3. 载入上下文管理器的 `__exit__()` 以便后续使用。
4. 发起调用上下文管理器的 `__enter__()` 方法。
5. 如果 with 语句中包含目标 target，来自 `__enter__()` 的返回值将被赋值给它。
6. 执行语句体。
7. 发起调用上下文管理器的 `__exit__()` 方法。

with 语句会保证如果 `__enter__()` 方法返回时未发生错误，则 `__exit__()` 将总是被调用。因此，如果在对目标赋值期间发生错误，则会将其视为在语句体内部发生的错误。

如果语句体的退出是由异常导致的，则其类型、值和回溯信息将被作为参数传递给 `__exit__()`。否则的话，将提供三个 None 参数（相当于无异常地退出）。

如果语句体的退出是由异常导致的，并且来自 `__exit__()` 方法的返回值为真，则该异常会被抑制，并会继续执行 with 语句之后的语句。如果返回值为假，则该异常会被重新引发（`__exit__()` 方法不应该重新引发被传入的异常，这是调用者的责任）。

如果语句体由于异常以外的任何原因退出，则来自 `__exit__()` 的返回值会被忽略，并会在该类退出正常的发生位置继续执行。

以下代码:
```
with EXPRESSION as TARGET:
    SUITE
```

在语义上等价于:
```
manager = (EXPRESSION)
enter = type(manager).__enter__
exit = type(manager).__exit__
value = enter(manager)
hit_except = False # False 表示正常执行

try:
    TARGET = value
    SUITE
except:
    hit_except = True # 发生了异常
    # 忽略或抑制异常，继续退出；或退出并引发异常
    if not exit(manager, *sys.exc_info()):
        raise
finally:
    if not hit_except: # 正常执行
        # 正常退出
        exit(manager, None, None, None)
```

可见使用 with 语句，无论有没有发生异常，都会 “清理” 程序（保存和恢复各种全局状态，锁定和解锁资源，关闭打开的文件等等）。

有多个表达式，则会视作存在多个 with 语句嵌套来处理多个上下文管理器:
```
with A() as a, B() as b:
    SUITE

# 在语义上等价于:
with A() as a:
    with B() as b:
        SUITE
```

with 语句常用来打开文件而不需要显式地关闭文件：


```python
with open('../11_built-in_function/test.txt',
          'r', encoding='utf-8') as f:
    print(f.read())
```

    xue.cn
    
    自学是门手艺
    


```python
# 相当于
f = open('../11_built-in_function/test.txt',
         'r', encoding='utf-8')
print(f.read())
f.close()
```

    xue.cn
    
    自学是门手艺
    
