## while 循环

while 语句用于在表达式保持为真的情况下重复地执行。语法如下：
```
while assignment_expression:
    suite
else: # 可选子句
    suite
```

对于简单语句可以写为一行，但不推荐。

这将重复地检验表达式，如果其值为真就执行其下的代码；表达式值为假则如果 else 子句存在就会被执行并终止循环。


```python
i = 0
while i < 3: print(i); i += 1
```

    0
    1
    2
    


```python
i = 0
while i < 3: 
    print(i)
    i += 1
else: # i 为 3 时执行
    print(f'i={i}')
    print('end')
```

    0
    1
    2
    i=3
    end
    
