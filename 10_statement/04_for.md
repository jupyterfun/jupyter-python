## for 循环

for 语句用于对可迭代对象中的元素进行迭代。语法如下：
```
for target_list in expression_list:
    suite
else: # 可选子句
    suite
```

对于简单语句可以写为一行，但不推荐。

表达式 expression_list 被求值一次，它应该产生一个可迭代对象。系统将为 expression_list 的结果创建一个迭代器，然后每一项会按标准赋值规则（详见见 [赋值语句](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/10_statement/02_assignment.ipynb)）被依次赋值给 target_list，每赋值一次执行一次语句下的代码。

当所有项被耗尽时，else 子句如果存在将会被执行，并终止循环。


```python
for i in range(3):print(i)
```

    0
    1
    2
    


```python
for i in zip('123','abc'):
    print(i)
```

    ('1', 'a')
    ('2', 'b')
    ('3', 'c')
    


```python
for i,j in zip('123','abc'):
    print(f'{i}->{j}')
else:
    print('end')
```

    1->a
    2->b
    3->c
    end
    

for 循环会对 target_list 中的变量进行赋值。这将覆盖之前对这些变量的所有赋值，包括在 for 循环体中的赋值。

变量在循环结束时不会被删除，但如果序列为空，则它们根本不会被循环所赋值。


```python
i = 'a'
for i in range(3):
    print(i)
print(i)
```

    0
    1
    2
    2
    


```python
for i in range(0):
    print(i)
print(i)
```

    2
    
