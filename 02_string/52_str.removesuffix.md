## str.removesuffix 移除后缀

字符串方法 str.removesuffix()。

3.9 版本新功能。

str.removesuffix(suffix, /)，如果字符串以 后缀字符串 suffix 结尾，并且后缀非空，返回 string[:-len(suffix)]，否则，返回原始字符串的副本。

```python
>>> 'MiscTests'.removesuffix('Tests')
'Misc'
>>> 'TmpDirMixin'.removesuffix('Tests')
'TmpDirMixin'
```
