## 实例

实例是调用类对象创建的具体对象。例如调用内置类型 int，创建的所有整数，都是 int 类的实例。可通过内置函数 isinstance() 进行实例检查。


```python
int('1')
```




    1




```python
isinstance(1,int)
```




    True



Python 中所有的实例对象，都是 object 的实例。所有的类都是 object 的子类，也被视为 object 的实例；所有的类也被视为默认的元类（创建类的类）type 的实例。

如果一个实例对象应该视为某个类的实例，可以通过魔法方法 `__instancecheck__()` 来重载 isinstance() 函数，自定义实例检查行为。


```python
isinstance(1,object), isinstance([],object)
```




    (True, True)




```python
isinstance(int,object)
```




    True




```python
isinstance(int,type)
```




    True



下面定义一个 “人” 类，来对实例进行说明：


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
```

上述 “人” 类对象 Person 是类对象，调用类对象创建的 xm 和 xz，是两个具体的 “人”，是实例对象。


```python
Person
```




    __main__.Person




```python
xm
```




    <__main__.Person at 0x24cf9ef6d68>




```python
xz
```




    <__main__.Person at 0x24cf9ef6d30>




```python
isinstance(xm, Person), isinstance(xz, Person)
```




    (True, True)




```python
isinstance(Person, object), isinstance(Person, type)
```




    (True, True)


