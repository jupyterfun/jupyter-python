## str.removeprefix  移除前缀

字符串方法 str.removeprefix()。

3.9 版本新功能。

str.removeprefix(prefix, /)，如果字符串以 前缀字符串 prefix 开头，返回 string[len(prefix):]，否则，返回原始字符串的副本。

```python
>>> 'TestHook'.removeprefix('Test')
'Hook'
>>> 'BaseTestCase'.removeprefix('Test')
'BaseTestCase'
```
