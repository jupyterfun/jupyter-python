## 方法

方法指在类内部定义的函数。但并不严格要求一定要在类内部定义。


```python
def f(self):
    pass

class A:
    f = f
A().f
```




    <bound method f of <__main__.A object at 0x00000290DC56E198>>



下列方法看起来是模块中的函数，其实是模块中，类实例方法重新赋值的名称：


```python
from random import randint
type(randint)
```




    method




```python
import random
# randint 完整路径
random.Random.randint

# 例如重新赋值后即可直接调用
r = random.Random()
randint = r.randint
randint(0,3)
```




    2



普通方法（第一个参数通常命名为 self）如果作为该类的实例的一个属性来调用，方法将会获取实例对象作为其第一个参数。


```python
# list 类的方法 append
help('list.append')
```

    Help on method_descriptor in list:
    
    list.append = append(self, object, /)
        Append object to the end of the list.
    
    


```python
# list 的实例 [] 调用，
# 方法将会获取实例对象 [] 作为其第一个参数
a = []
a.append(1)
a
```




    [1]




```python
# 等价于
a = []
list.append(a,1)
a
```




    [1]



类方法（第一个参数通常命名为 cls）则无论是类或是实例调用，方法都将获取类对象作为其第一个参数。类方法定义详见 [classmethod 封装函数为类方法](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/11_built-in_function/10_classmethod.ipynb)。


```python
class A:
    @classmethod
    def f(cls,x):
        print(cls,x)
        
print(f'A = {A}')        
A.f('类方法')
A().f('类方法')
```

    A = <class '__main__.A'>
    <class '__main__.A'> 类方法
    <class '__main__.A'> 类方法
    

静态方法则不会接收隐式的第一个参数。调用它需要正常传递参数。静态方法详见 [staticmethod 封装函数为静态方法](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/11_built-in_function/58_staticmethod.ipynb)。


```python
class A:
    @staticmethod
    def in_print(value):
        print(value)
        
a = A()
a.in_print('静态方法')
A.in_print('静态方法')
```

    静态方法
    静态方法
    

特殊方法（也称魔术方法）：一种由 Python 隐式调用的方法，用来对某个类型执行特定操作例如相加等等。这种方法的名称的首尾都为双下划线。可以通过方法重载，对某个类型定义特定操作。


```python
# 1 + 2 操作其实是隐式调用了 __add__
1 + 2
```




    3




```python
(1).__add__(2)
```




    3




```python
# 列表没有 “-” 操作符，自定义一个
class Mlist(list):
    def __sub__(self, other):
        return list(set(self) - set(other))
    
a = Mlist('123')
b = Mlist('13')
a, b, a - b
```




    (['1', '2', '3'], ['1', '3'], ['2'])


