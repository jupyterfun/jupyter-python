## 文件对象概述

文件对象是指对外提供面向文件 API 以使用下层资源的对象（带有 read() 或 write() 这样的方法），也被称作**流**或**文件类对象**。

有三种类别的文件对象: 原始二进制文件, 缓冲二进制文件 以及
文本文件。三种类别下还有子类别，因创建方式的不同得到不同类别文件对象。它们的接口定义均在 io 模块中。创建文件对象的规范方式是使用 [open() 函数](https://xue.cn/hub/reader?bookId=64&path=xue_python_kp/11_built-in_function/45_open.ipynb)。

用户代码直接操作原始流的用法非常罕见。不过，可以通过在禁用缓冲的情况下以二进制模式打开文件来创建原始流：


```python
f = open("test.txt","rb", buffering=0)
f
```




    <_io.FileIO name='test.txt' mode='rb' closefd=True>



缓冲二进制流不执行编码、解码或换行转换。这种类型的流可以用于所有类型的非文本数据（例如图片，视频），并且还可以在需要手动控制文本数据的处理时使用。创建缓冲二进制流的最简单方法是使用 open()，并在模式中指定 'b'：


```python
f = open("test.txt","rb")
f
```




    <_io.BufferedReader name='test.txt'>



文本流生成 str 对象。这意味着，无论何时后台存储是由字节组成的，数据的编码和解码都是透明的，并且可以选择转换特定于平台的换行符。创建文本流的最简单方法是使用 open()，可以选择指定编码：


```python
f = open("test.txt",encoding="utf-8")
f
```




    <_io.TextIOWrapper name='test.txt' mode='r' encoding='utf-8'>



所有流对提供给它们的数据类型都很敏感。例如将 str 对象给二进制流的 write() 方法会引发 TypeError。


```python
f = open("test.txt","ab")
f.write('写入内容')
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-19-a9efd264aca2> in <module>
          1 f = open("test.txt","ab")
    ----> 2 f.write('写入内容')
    

    TypeError: a bytes-like object is required, not 'str'


内存中的流也可以作为文件对象使用：


```python
import io
f = io.StringIO("some initial text data")
print(f)
f.read()
```

    <_io.StringIO object at 0x000001BE348D2040>
    




    'some initial text data'




```python
f = io.BytesIO(b"some initial binary data: \x00\x01")
print(f)
f.read()
```

    <_io.BytesIO object at 0x000001BE348D3310>
    




    b'some initial binary data: \x00\x01'



open() 函数打开文件，创建流后，会使文件在一段不确定的时间内处于打开状态。这在简单脚本中不是问题，但对于较大的应用程序来说可能是个问题。此时用 close() 方法刷新并关闭流（或直接使用 with 语句打开）是明智的做法。


```python
f = open("test.txt",encoding="utf-8")
print(f.read())
f.close()
```

    为什么要掌握自学能力？
    未来还很长。
    
