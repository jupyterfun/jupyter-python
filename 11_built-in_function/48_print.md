## print() 打印对象

内置函数 print()，Python 官方文档描述如下：


```python
help(print)
```

    Help on built-in function print in module builtins:
    
    print(...)
        print(value, ..., sep=' ', end='\n', file=sys.stdout, flush=False)
        
        Prints the values to a stream, or to sys.stdout by default.
        Optional keyword arguments:
        file:  a file-like object (stream); defaults to the current sys.stdout.
        sep:   string inserted between values, default a space.
        end:   string appended after the last value, default a newline.
        flush: whether to forcibly flush the stream.
    
    

将 value ... 打印到 file 指定的文本流，以 sep 分隔并在末尾加上 end。sep, end, file 和 flush 如果存在，它们必须以关键字参数的形式给出。

所有非关键字参数都会被转换为字符串，就像是执行了 str() 一样，并会被写入到流。sep 和 end 都必须为字符串。sep 默认为一个空格 ' '，end 默认为换行 '\n'。

如果没有给出 value ...，则 print() 将只打印 end。

file 参数必须是一个具有 `write(string)` 方法的对象。如果参数不指定，则将使用解释器用于标准输出的文件对象 sys.stdout。

输出是否被缓存通常决定于 file，但如果 flush 关键字参数为真值，流会被强制刷新。

该函数返回值为 None。


```python
print(1+1)
print('a','b')
```

    2
    a b
    


```python
print('a',1,int, sep='-', end='end')
```

    a-1-<class 'int'>end


```python
print(end='end')
```

    end


```python
p = print('end')
print(p)
```

    end
    None
    
