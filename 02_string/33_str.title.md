## str.title 单词首字母大写

字符串方法 str.title()，Python 官方文档描述如下：


```python
help(str.title)
```

    Help on method_descriptor:
    
    title(self, /)
        Return a version of the string where each word is titlecased.
        
        More specifically, words start with uppercased characters and all remaining
        cased characters have lower case.
    
    

返回原字符串的标题版本，其中每个单词第一个字母为大写，其余字母为小写。


```python
'hi python'.title()
```




    'Hi Python'




```python
'嗨python'.title()
```




    '嗨Python'



该算法使用一种简单的与语言无关的定义，将连续的字母组合视为单词。该定义在多数情况下都很有效，但它也意味着代表缩写形式与所有格的撇号也会成为单词边界，这可能导致不希望的结果:


```python
"they're bill's friends from the UK".title()
```




    "They'Re Bill'S Friends From The Uk"


