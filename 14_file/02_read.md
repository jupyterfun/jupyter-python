## 读取文件内容

打开方式不同，会创建不同类型的文件对象（流），不同类型的文件对象，可能有不同的属性或方法。

下列检查或读取内容的属性或方法，是多数文件对象通用的：

- readable() 如果可以读取流，则返回 True 。否则为 False ，且 read() 将引发 OSError 错误。


```python
f = open('test.txt')
f.readable()
```




    True



- read(size=-1) 从对象中读取 size 个字节并将其返回。作为一个便捷选项，如果 size 未指定或为 -1，则返回所有字节直到 EOF。流的位置与读取内容同步，不重设流的位置，内容只能被读取一次。

- tell() 返回当前流的位置。


```python
f = open('test.txt',encoding='utf-8')
f.read()
```




    '为什么一定要掌握自学能力？\n未来的日子还很长，\n这世界进步得太快，\n没有自学能力，\n没有未来。'




```python
f = open('test.txt',encoding='utf-8')
f.read(12)
```




    '为什么一定要掌握自学能力'




```python
f.tell()
```




    36




```python
f.read() # 再次读取，将读取剩下未读部分
```




    '？\n未来的日子还很长，\n这世界进步得太快，\n没有自学能力，\n没有未来。'




```python
f.read() # 已经没有内容
```




    ''



- seek(offset, whence=0) 将流位置修改到给定的字节 offset。返回新的绝对位置。


```python
f.seek(0, 0)
```




    0




```python
f.read() # 从新位置读取
```




    '为什么一定要掌握自学能力？\n未来的日子还很长，\n这世界进步得太快，\n没有自学能力，\n没有未来。'



- readline(size=-1) 从流中读取并返回一行。如果指定了 size，将至多读取 size 个字节。


```python
f = open('test.txt',encoding='utf-8')
f.readline()
```




    '为什么一定要掌握自学能力？\n'




```python
f.readline(2) # 再次读取，将读取剩下未读部分
```




    '未来'



- readlines(hint=-1) 从流中读取并返回包含多行的列表。可以指定 hint 来控制要读取的行数。指定行数可以多于实际。


```python
f = open('test.txt',encoding='utf-8')
f.readlines(1)
```




    ['为什么一定要掌握自学能力？\n']




```python
f.readlines(10) # 再次读取，将读取剩下未读部分
```




    ['未来的日子还很长，\n', '这世界进步得太快，\n']



- 使用 `for line in file: ...` 就足够对文件对象进行迭代了，可以不必调用 file.readlines()。


```python
f = open('test.txt',encoding='utf-8')
for line in f:
    print(line)
```

    为什么一定要掌握自学能力？
    
    未来的日子还很长，
    
    这世界进步得太快，
    
    没有自学能力，
    
    没有未来。
    

- closed 如果流已关闭，则返回 True。


```python
f.closed
```




    False



- close() 刷新并关闭此流。无论读写操作，最后都应该关闭流。如果文件已经关闭，则此方法无效。文件关闭后，对文件的任何操作（例如读取或写入）都会引发 ValueError 。为方便起见，允许多次调用此方法。但是，只有第一个调用才会生效。


```python
f.close()
f.close()
f.closed
```




    True


