## input() 接受输入返回字符串

内置函数 input()，Python 官方文档描述如下：


```python
help(input)
```

    Help on method raw_input in module ipykernel.kernelbase:
    
    raw_input(prompt='') method of ipykernel.ipkernel.IPythonKernel instance
        Forward raw_input to frontends
        
        Raises
        ------
        StdinNotImplentedError if active frontend doesn't support stdin.
    
    

如果存在 prompt 实参，则作为提示信息输出。接下来，该函数将输入转换为字符串并返回。无输入则返回空字符串。


```python
input('输入提示：')
```

    输入提示： 1+1
    




    '1+1'




```python
input('输入提示：')
```

    输入提示： 
    




    ''


