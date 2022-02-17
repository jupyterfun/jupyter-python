## open() 打开文件

内置函数 open()，Python 官方文档描述如下：


```python
help(open)
```

    Help on built-in function open in module io:
    
    open(file, mode='r', buffering=-1, encoding=None, errors=None, newline=None, closefd=True, opener=None)
        Open file and return a stream.  Raise OSError upon failure.
        
        file is either a text or byte string giving the name (and the path
        if the file isn't in the current working directory) of the file to
        be opened or an integer file descriptor of the file to be
        wrapped. (If a file descriptor is given, it is closed when the
        returned I/O object is closed, unless closefd is set to False.)
        
        mode is an optional string that specifies the mode in which the file
        is opened. It defaults to 'r' which means open for reading in text
        mode.  Other common values are 'w' for writing (truncating the file if
        it already exists), 'x' for creating and writing to a new file, and
        'a' for appending (which on some Unix systems, means that all writes
        append to the end of the file regardless of the current seek position).
        In text mode, if encoding is not specified the encoding used is platform
        dependent: locale.getpreferredencoding(False) is called to get the
        current locale encoding. (For reading and writing raw bytes use binary
        mode and leave encoding unspecified.) The available modes are:
        
        ========= ===============================================================
        Character Meaning
        --------- ---------------------------------------------------------------
        'r'       open for reading (default)
        'w'       open for writing, truncating the file first
        'x'       create a new file and open it for writing
        'a'       open for writing, appending to the end of the file if it exists
        'b'       binary mode
        't'       text mode (default)
        '+'       open a disk file for updating (reading and writing)
        'U'       universal newline mode (deprecated)
        ========= ===============================================================
        
        The default mode is 'rt' (open for reading text). For binary random
        access, the mode 'w+b' opens and truncates the file to 0 bytes, while
        'r+b' opens the file without truncation. The 'x' mode implies 'w' and
        raises an `FileExistsError` if the file already exists.
        
        Python distinguishes between files opened in binary and text modes,
        even when the underlying operating system doesn't. Files opened in
        binary mode (appending 'b' to the mode argument) return contents as
        bytes objects without any decoding. In text mode (the default, or when
        't' is appended to the mode argument), the contents of the file are
        returned as strings, the bytes having been first decoded using a
        platform-dependent encoding or using the specified encoding if given.
        
        'U' mode is deprecated and will raise an exception in future versions
        of Python.  It has no effect in Python 3.  Use newline to control
        universal newlines mode.
        
        buffering is an optional integer used to set the buffering policy.
        Pass 0 to switch buffering off (only allowed in binary mode), 1 to select
        line buffering (only usable in text mode), and an integer > 1 to indicate
        the size of a fixed-size chunk buffer.  When no buffering argument is
        given, the default buffering policy works as follows:
        
        * Binary files are buffered in fixed-size chunks; the size of the buffer
          is chosen using a heuristic trying to determine the underlying device's
          "block size" and falling back on `io.DEFAULT_BUFFER_SIZE`.
          On many systems, the buffer will typically be 4096 or 8192 bytes long.
        
        * "Interactive" text files (files for which isatty() returns True)
          use line buffering.  Other text files use the policy described above
          for binary files.
        
        encoding is the name of the encoding used to decode or encode the
        file. This should only be used in text mode. The default encoding is
        platform dependent, but any encoding supported by Python can be
        passed.  See the codecs module for the list of supported encodings.
        
        errors is an optional string that specifies how encoding errors are to
        be handled---this argument should not be used in binary mode. Pass
        'strict' to raise a ValueError exception if there is an encoding error
        (the default of None has the same effect), or pass 'ignore' to ignore
        errors. (Note that ignoring encoding errors can lead to data loss.)
        See the documentation for codecs.register or run 'help(codecs.Codec)'
        for a list of the permitted encoding error strings.
        
        newline controls how universal newlines works (it only applies to text
        mode). It can be None, '', '\n', '\r', and '\r\n'.  It works as
        follows:
        
        * On input, if newline is None, universal newlines mode is
          enabled. Lines in the input can end in '\n', '\r', or '\r\n', and
          these are translated into '\n' before being returned to the
          caller. If it is '', universal newline mode is enabled, but line
          endings are returned to the caller untranslated. If it has any of
          the other legal values, input lines are only terminated by the given
          string, and the line ending is returned to the caller untranslated.
        
        * On output, if newline is None, any '\n' characters written are
          translated to the system default line separator, os.linesep. If
          newline is '' or '\n', no translation takes place. If newline is any
          of the other legal values, any '\n' characters written are translated
          to the given string.
        
        If closefd is False, the underlying file descriptor will be kept open
        when the file is closed. This does not work when a file name is given
        and must be True in that case.
        
        A custom opener can be used by passing a callable as *opener*. The
        underlying file descriptor for the file object is then obtained by
        calling *opener* with (*file*, *flags*). *opener* must return an open
        file descriptor (passing os.open as *opener* results in functionality
        similar to passing None).
        
        open() returns a file object whose type depends on the mode, and
        through which the standard file operations such as reading and writing
        are performed. When open() is used to open a file in a text mode ('w',
        'r', 'wt', 'rt', etc.), it returns a TextIOWrapper. When used to open
        a file in a binary mode, the returned class varies: in read binary
        mode, it returns a BufferedReader; in write binary and append binary
        modes, it returns a BufferedWriter, and in read/write mode, it returns
        a BufferedRandom.
        
        It is also possible to use a string or bytearray as a file for both
        reading and writing. For strings StringIO can be used like a file
        opened in a text mode, and for bytes a BytesIO can be used like a file
        opened in a binary mode.
    
    

打开文件 file 并返回对应的文件对象（file object）。

参数说明：

1，file 是将要打开的文件的路径（绝对路径或者当前工作目录的相对路径），也可以是要被封装的整数类型文件描述符。（如果是文件描述符，它会随着返回的 I/O 对象关闭而关闭，除非 closefd 被设为 False ）。

2，mode 是一个可选字符串，用于指定打开文件的模式。默认值是 'r' ，这意味着它以文本模式打开并读取。在文本模式，如果 encoding 没有指定，则根据平台来决定使用的编码（要读取和写入原始字节，请使用二进制模式并不要指定 encoding）。可用的模式有：
- 'r' 读取（默认）
- 'w' 写入，并先截断文件（会删除原内容），文件不存在则创建
- 'x' 排它性创建，如果文件已存在则失败
- 'a' 写入，如果文件存在则在末尾追加，不存在则创建
- 'b' 二进制模式
- 't' 文本模式（默认）
- '+' 打开用于更新（读取与写入）

模式 'r'，'w'，'x'，'a' 可以单独使用，也可与 'b' 或 '+'，或两者同时组合使用。'b'，'t' 和 '+' 不能单独使用。'b' 和 't' 互斥，'t' 默认省略。

默认模式为 'r' (打开用于读取文本，与 'rt' 同义)。模式 'w+' 与 'w+b' 打开文件并清空内容。模式 'r+' 与 'r+b' 打开文件并不清空内容。

以二进制模式打开的文件返回的内容为字节串，不进行任何解码。在文本模式下打开时，文件内容返回为字符串，首先使用指定的 encoding （如果给定）或者使用平台默认的的字节编码解码。

3，buffering 是一个可选的整数，用于设置缓冲策略。

4，encoding 是用于解码或编码文件的编码的名称。这应该只在文本模式下使用。

5，errors 是一个可选的字符串参数，用于指定如何处理编码和解码错误。这不能在二进制模式下使用。

6，newline 控制通用换行模式如何生效（它仅适用于文本模式）。

7，如果 closefd 是 False 并且打开文件给出了文件描述符而不是文件名，那么当文件关闭时，底层文件描述符将保持打开状态。如果给出文件名则 closefd 必须为 True （默认值），否则将引发错误。

8，可以通过传递可调用的 opener 来使用自定义开启器。


```python
with open('test.txt') as f:
    print(f)
```

    <_io.TextIOWrapper name='test.txt' mode='r' encoding='cp936'>
    


```python
with open('test.txt',encoding='utf-8') as f:
    print(f.read())
```

    xue.cn
    
    自学是门手艺
    


```python
with open('test.txt','rb') as f:
    print(f.read())
```

    b'xue.cn\r\n\r\n\xe8\x87\xaa\xe5\xad\xa6\xe6\x98\xaf\xe9\x97\xa8\xe6\x89\x8b\xe8\x89\xba'
    
