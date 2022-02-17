## nonlocal 语句

nonlocal 语句会使得所列出的名称指向在它之前**已经存在**的，**和它最近**并且**在包含它的作用域中绑定**，**除全局变量以外**的变量。

这种功能很重要，因为绑定的默认行为是先搜索局部命名空间。这个语句允许被封装的代码重新绑定局部作用域以外且非全局（模块）作用域当中的变量。

举例如下：


```python
a = '全局'
def f():
    a = 'f' # f 中已经存在的 a, 包含 f2
    
    def f1():
        a = 'f1' # f1 中的局部变量
        
    def f2():
        nonlocal a # 和他最近且包含的是 'f'
        a = 'f2'
        
    def f3():
        global a
        a = 'f3'
    # 调用 f1 不改变 a = 'f'    
    f1() 
    print(a)
    # 调用 f2, nonlocal 将 a = 'f' 重新绑定为 a = 'f2'
    f2() 
    print(a)
    # 调用 f3, global 将 a 声明为全局变量，
    # 并将 a = '全局' 重新绑定为 a = 'f3' 
    # 但在 f 这个局部中，a 仍然是 'f2'
    f3()
    print(a)

f() # 调用 f 使绑定都生效
print(a)
```

    f
    f2
    f2
    f3
    


```python
# 不存在不可以绑定
def f():
    nonlocal a 
    a = 1
f()
```


      File "<ipython-input-3-3706e217f701>", line 2
        nonlocal a
        ^
    SyntaxError: no binding for nonlocal 'a' found
    



```python
# 不是包含它的作用域，不可以绑定
def f():
    def f1():
        a = 0
    f1()
    nonlocal a 
    a = 1
f()
```


      File "<ipython-input-4-a036260d029b>", line 5
        nonlocal a
        ^
    SyntaxError: no binding for nonlocal 'a' found
    



```python
# 全局变量，不可以绑定
a = 0
def f():
    nonlocal a 
    a = 1
f()
```


      File "<ipython-input-5-87297c0b0eeb>", line 4
        nonlocal a
        ^
    SyntaxError: no binding for nonlocal 'a' found
    

