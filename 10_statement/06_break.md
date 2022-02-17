## break 语句

break 在语法上只会出现于 for 或 while 循环所嵌套的代码。

它会终结最近的外层循环，如果循环有可选的 else 子句，也会跳过该子句。

如果一个 for 循环被 break 所终结，该循环的控制变量会保持其当前值。

当 break 将控制流传出一个带有 finally 子句的 try 语句时，该  finally 子句会先被执行然后再真正离开该循环。


```python
for i in range(6):
    for j in range(6):
        if i**2 == j:
            print(f'i={i},j={j}')
print(f'i={i},j={j}')            
```

    i=0,j=0
    i=1,j=1
    i=2,j=4
    i=5,j=5
    


```python
for i in range(6):
    for j in range(6):
        if i**2 == j:
            print(f'i={i},j={j}')
        break
print(f'i={i},j={j}')  
```

    i=0,j=0
    i=5,j=0
    


```python
for i in range(6):
    for j in range(6):
        if i**2 == j:
            print(f'i={i},j={j}')
        break # 控制内层循环
    else: # 不会执行
        print(f'i={i},j={j}')  
```

    i=0,j=0
    


```python
for i in range(6):
    for j in range(6):
        if i**2 == j:
            print(f'i={i},j={j}')
        break
else: # 属于外层循环，会执行
    print(f'i={i},j={j}')  
```

    i=0,j=0
    i=5,j=0
    


```python
for i in range(5):
    try:
        print(f'3/i={3/i}')
    except ZeroDivisionError as e:
        print(e)
    finally:
        print(f'i={i}')
```

    division by zero
    i=0
    3/i=3.0
    i=1
    3/i=1.5
    i=2
    3/i=1.0
    i=3
    3/i=0.75
    i=4
    


```python
# 引发异常直接跳过 break
# 无异常则继续执行完 finally 才终止循环
for i in range(5):
    try:
        print(f'3/i={3/i}')
        break
    except ZeroDivisionError as e:
        print(e)
    finally:
        print(f'i={i}')
```

    division by zero
    i=0
    3/i=3.0
    i=1
    
