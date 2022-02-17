## 文件写入内容

打开方式不同，会创建不同类型的文件对象（流），不同类型的文件对象，可能有不同的属性或方法。

打开模式不同，写入内容的方式也会不同，详见 [open() 打开文件](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/11_built-in_function/45_open.ipynb)。

下列检查或写入内容的属性或方法，是多数文件对象通用的：

- writable() 如果流支持写入则返回 True。如为 False，则 write() 将引发 OSError。


```python
f = open('test.txt','a',encoding='utf-8')
f.writable()
```




    True




```python
f = open('test.txt')
f.writable()
f.write('这世界进步得太快，')
```


    ---------------------------------------------------------------------------

    UnsupportedOperation                      Traceback (most recent call last)

    <ipython-input-1-7bf449cf8958> in <module>
          1 f = open('test.txt')
          2 f.writable()
    ----> 3 f.write('这世界进步得太快，')
    

    UnsupportedOperation: not writable


- write() 将字符串或字节串写入到流并返回写入的字符或字节数。对于阻塞流（需要刷新才能将内容写入文件），写入内容在缓冲区（打开文件看不到写入的内容）。


```python
f = open('test.txt','a+',encoding='utf-8')
f.write('\n这世界进步得太快，')
```




    10



- flush() 刷新流的写入缓冲区（打开文件将看到写入的内容）。这对只读和非阻塞流不起作用。


```python
f.flush()
```

- writelines(lines) 将行列表写入到流。不会添加行分隔符，因此通常所提供的每一行都带有末尾行分隔符。对于阻塞流，写入内容在缓冲区。


```python
f = open('test.txt','a+',encoding='utf-8')
f.writelines(['\n没有自学能力，\n', '没有未来。'])
```


```python
f.tell() # 流的位置在末尾
```




    137




```python
f.read() # 从末尾读取内容为空
```




    ''




```python
f.seek(0, 0) # 重设流的位置为开头
```




    0




```python
f.read()
```




    '为什么一定要掌握自学能力？\n未来的日子还很长，\n这世界进步得太快，\n没有自学能力，\n没有未来。'



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


