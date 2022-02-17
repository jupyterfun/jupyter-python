## 创建实例

直接调用类对象，即可创建该类的实例对象。


```python
int() # 调用 int 类
```




    0




```python
list('123') # 传参调用 list 类
```




    ['1', '2', '3']




```python
class A:
    def __init__(self, name):
        self.name = name
        
    def __repr__(self):
        return self.name
    
A('实例1'), A('实例2') # 调用自定义类
```




    (实例1, 实例2)



实例对象是由特殊方法 `__new__()` 创建，`__init__()` 定制完成。两个方法是隐式地完成创建和定制的，当然也可以显式地创建并定制。


```python
class A:
    def __init__(self):
        self.name = '实例'
        
A # 类对象 A
```




    __main__.A




```python
# 显式地创建类 A 的一个实例 a
a = object.__new__(A)
a
```




    <__main__.A at 0x20d23e95d30>




```python
# 未初始化，无属性
a.name
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-36-b3a4d04d98fc> in <module>
          1 # 未初始化，无属性
    ----> 2 a.name
    

    AttributeError: 'A' object has no attribute 'name'



```python
# 也可以使用 a.__init__(), 
# 它会自动将实例作为第一个参数完成初始化
A.__init__(a)
a
```




    <__main__.A at 0x20d23e95d30>




```python
a.name
```




    '实例'


