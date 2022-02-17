## 类定义

类是用来创建用户定义对象的模板，是抽象的对象（类对象）。例如我们说鱼类，指的就是一类抽象的对象，而具体到武昌鱼，鲈鱼，鲫鱼…… 就是具体的对象。

定义了一个类，就可以用这个模块来创建它的具体对象（实例）。类定义的详细语法规则见 [class 定义类](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/10_statement/13_class.ipynb)。

创建一个类，需要继承另一个类。新创建的类是子类，继承的类是基类。如不指定，创建类默认继承自所有类的基类 object。

下面是一个没有任何自定义属性的简单类：


```python
class A:
    pass

A
```




    __main__.A




```python
type(A)
```




    type




```python
A.__bases__ # 查看基类
```




    (object,)



继承一个指定的类，可以对它进行定制化开发。需要注意参数 self, 它是约定名称（可自定义但不推荐），它就代表类创建的实例对象自身。

例如创建一个自定义的列表类，增加 add() 方法：


```python
class Mylist(list):
    def add(self,value):
        self.append(value)
        
lst = Mylist('123') # 创建实例赋值给 lst
lst.add(4) # lst 调用 add 方法，self 参数就是 lst
lst
```




    ['1', '2', '3', 4]



或者自定义一个字典，当访问的键不存在时，不报错，而是返回 None（`__missing__()` 是用来定义字典子类时找不到键如何处理的魔法方法）：


```python
class Mydict(dict):
    def __missing__(self, key):
        return 

d = Mydict(a=1,b=2)
d, d['c']
```




    ({'a': 1, 'b': 2}, None)



我们也可以自定义任意的类，其中 `__init__()` 方法是创建实例时用来初始化实例对象的魔法方法，可以用它来增加一些自定义属性。没有该方法，创建实例时，将自动调用基类的该方法完成初始化。

例如定义一个 “人” 类：


```python
class Person:
    '这是人类'
    # 定义人的属性
    def __init__(self, name):
        self.name = name
        self.ears = '耳朵'
        self.brain = '大脑'
        self.hands = '双手'
    
    # 人有生活
    def live(self):
        print(f'{self.name}用{self.ears}'
              '听着音乐，'
              '享受美好生活。')
        
    # 还有工作
    def work(self):
        print(f'{self.name}用{self.brain}和'
              f'{self.hands}'
               '勤劳致富。')
        
# 造人
xm = Person('小明')
xz = Person('小张')
xm.live() # 小明在享受生活
xz.work() # 小张在努力工作
```

    小明用耳朵听着音乐，享受美好生活。
    小张用大脑和双手勤劳致富。
    
