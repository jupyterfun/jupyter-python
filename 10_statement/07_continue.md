## continue 语句

continue 在语法上只会出现于 for 或 while 循环所嵌套的代码中。

它会继续执行最近的外层循环的下一个轮次，或者在没有下一轮次时转往  else 子句执行。

当 continue 将控制流传出一个带有 finally 子句的 try 语句时，该  finally 子句会先被执行然后再真正开始循环的下一个轮次。


```python
for i in range(3):
    for j in range(3):
        if j == 1:
            print(f'i={i},j={j}')
        continue
```

    i=0,j=1
    i=1,j=1
    i=2,j=1
    


```python
for i in range(3):
    for j in range(3):
        if j == 2:
            print(f'i={i},j={j}')
        continue
    else: # 属于内层循环，每次内层循环结束都执行
        print('end')
```

    i=0,j=2
    end
    i=1,j=2
    end
    i=2,j=2
    end
    


```python
for i in range(3):
    for j in range(3):
        if j == 2:
            print(f'i={i},j={j}')
        continue
else: # 属于外层循环，外层循环结束才执行
    print('end')
```

    i=0,j=2
    i=1,j=2
    i=2,j=2
    end
    


```python
# 引发异常直接跳过 continue
# 无异常则继续执行完 finally 才继续下一次循环
for i in range(3):
    try:
        print(f'3/i={3/i}')
        continue
    except ZeroDivisionError as e:
        print(e)
    finally:
        print(f'i={i}')
    print(i) # 无异常时被跳过
else:
    print('end')
```

    division by zero
    i=0
    0
    3/i=3.0
    i=1
    3/i=1.5
    i=2
    end
    
