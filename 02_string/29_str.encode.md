## str.encode 编码为字节串

字符串方法 str.encode()，Python 官方文档描述如下：


```python
help(str.encode)
```

    Help on method_descriptor:
    
    encode(self, /, encoding='utf-8', errors='strict')
        Encode the string using the codec registered for encoding.
        
        encoding
          The encoding in which to encode the string.
        errors
          The error handling scheme to use for encoding errors.
          The default is 'strict' meaning that encoding errors raise a
          UnicodeEncodeError.  Other possible values are 'ignore', 'replace' and
          'xmlcharrefreplace' as well as any other name registered with
          codecs.register_error that can handle UnicodeEncodeErrors.
    
    

返回原字符串编码为字节串对象的版本。默认编码为 'utf-8'。可以给出 errors 来设置不同的错误处理方案。errors 的默认值为 'strict'，表示编码错误会引发 UnicodeError。

下列为 'utf-8' 和 'gbk' 两种编码比较：


```python
'嗨 python'.encode()
```




    b'\xe5\x97\xa8 python'




```python
'嗨 python'.encode('gbk')
```




    b'\xe0\xcb python'




```python
'▲ python'.encode('gbk')
```




    b'\xa1\xf8 python'




```python
'🔺 python'.encode()
```




    b'\xf0\x9f\x94\xba python'




```python
'🔺 python'.encode('gbk') #gbk 不能编码 🔺
```


    ---------------------------------------------------------------------------

    UnicodeEncodeError                        Traceback (most recent call last)

    <ipython-input-15-60e87a9208be> in <module>
    ----> 1 '🔺 python'.encode('gbk')
    

    UnicodeEncodeError: 'gbk' codec can't encode character '\U0001f53a' in position 0: illegal multibyte sequence


**拓展：**

将字节串解码为字符串用 bytes.decode:


```python
help(bytes.decode)
```


    [1;31mSignature:[0m [0mbytes[0m[1;33m.[0m[0mdecode[0m[1;33m([0m[0mself[0m[1;33m,[0m [1;33m/[0m[1;33m,[0m [0mencoding[0m[1;33m=[0m[1;34m'utf-8'[0m[1;33m,[0m [0merrors[0m[1;33m=[0m[1;34m'strict'[0m[1;33m)[0m[1;33m[0m[1;33m[0m[0m
    [1;31mDocstring:[0m
    Decode the bytes using the codec registered for encoding.
    
    encoding
      The encoding with which to decode the bytes.
    errors
      The error handling scheme to use for the handling of decoding errors.
      The default is 'strict' meaning that decoding errors raise a
      UnicodeDecodeError. Other possible values are 'ignore' and 'replace'
      as well as any other name registered with codecs.register_error that
      can handle UnicodeDecodeErrors.
    [1;31mType:[0m      method_descriptor
    



```python
b'\xf0\x9f\x94\xba python'.decode()
```




    '🔺 python'


