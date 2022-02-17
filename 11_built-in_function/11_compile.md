## compile() 创建代码对象

内置函数 compile()，Python 官方文档描述如下：


```python
help(compile)
```

    Help on built-in function compile in module builtins:
    
    compile(source, filename, mode, flags=0, dont_inherit=False, optimize=-1)
        Compile source into a code object that can be executed by exec() or eval().
        
        The source code may represent a Python module, statement or expression.
        The filename will be used for run-time error messages.
        The mode must be 'exec' to compile a module, 'single' to compile a
        single (interactive) statement, or 'eval' to compile an expression.
        The flags argument, if present, controls which future statements influence
        the compilation of the code.
        The dont_inherit argument, if true, stops the compilation inheriting
        the effects of any future statements in effect in the code calling
        compile; if absent or false these statements do influence the compilation,
        in addition to any features explicitly specified.
    
    

将 source 编译成代码或 AST 对象。代码对象可以被 exec() 或 eval() 执行。

参数说明：
- source，要编译的资源，可以是字符串、字节或 AST 对象。
- filename，源所来自的文件的名称。如果代码不需要从文件中读取，可以传入一些可辨识的值（经常会使用字符串）。
- mode，指定了编译代码必须用的模式。如果 source 是语句序列，可以是 'exec'；如果是单一表达式，可以是 'eval'；如果是单个交互式语句，可以是 'single'。
- flags	和 dont-inherit，控制在编译 source 时要用到哪个 future 语句。
- optimize，指定编译器的优化级别；默认值 -1 选择与解释器的 -O 选项相同的优化级别。


```python
source = 'for i in range(3):print(i)'
code = compile(source,'null','exec')
code
```




    <code object <module> at 0x000001E999B07780, file "null", line 1>




```python
exec(code)
```

    0
    1
    2
    


```python
eval(code)
```

    0
    1
    2
    
