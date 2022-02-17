## bytes 创建 bytes 对象

内置函数（类）bytes，Python 官方文档描述如下：


```python
help(bytes)
```

    Help on class bytes in module builtins:
    
    class bytes(object)
     |  bytes(iterable_of_ints) -> bytes
     |  bytes(string, encoding[, errors]) -> bytes
     |  bytes(bytes_or_buffer) -> immutable copy of bytes_or_buffer
     |  bytes(int) -> bytes object of size given by the parameter initialized with null bytes
     |  bytes() -> empty bytes object
     |  
     |  Construct an immutable array of bytes from:
     |    - an iterable yielding integers in range(256)
     |    - a text string encoded using the specified encoding
     |    - any object implementing the buffer API.
     |    - an integer
     |  
     |  Methods defined here:
     |  
     |  __add__(self, value, /)
     |      Return self+value.
     |  
     |  __contains__(self, key, /)
     |      Return key in self.
     |  
     |  __eq__(self, value, /)
     |      Return self==value.
     |  
     |  __ge__(self, value, /)
     |      Return self>=value.
     |  
     |  __getattribute__(self, name, /)
     |      Return getattr(self, name).
     |  
     |  __getitem__(self, key, /)
     |      Return self[key].
     |  
     |  __getnewargs__(...)
     |  
     |  __gt__(self, value, /)
     |      Return self>value.
     |  
     |  __hash__(self, /)
     |      Return hash(self).
     |  
     |  __iter__(self, /)
     |      Implement iter(self).
     |  
     |  __le__(self, value, /)
     |      Return self<=value.
     |  
     |  __len__(self, /)
     |      Return len(self).
     |  
     |  __lt__(self, value, /)
     |      Return self<value.
     |  
     |  __mod__(self, value, /)
     |      Return self%value.
     |  
     |  __mul__(self, value, /)
     |      Return self*value.
     |  
     |  __ne__(self, value, /)
     |      Return self!=value.
     |  
     |  __repr__(self, /)
     |      Return repr(self).
     |  
     |  __rmod__(self, value, /)
     |      Return value%self.
     |  
     |  __rmul__(self, value, /)
     |      Return value*self.
     |  
     |  __str__(self, /)
     |      Return str(self).
     |  
     |  capitalize(...)
     |      B.capitalize() -> copy of B
     |      
     |      Return a copy of B with only its first character capitalized (ASCII)
     |      and the rest lower-cased.
     |  
     |  center(...)
     |      B.center(width[, fillchar]) -> copy of B
     |      
     |      Return B centered in a string of length width.  Padding is
     |      done using the specified fill character (default is a space).
     |  
     |  count(...)
     |      B.count(sub[, start[, end]]) -> int
     |      
     |      Return the number of non-overlapping occurrences of subsection sub in
     |      bytes B[start:end].  Optional arguments start and end are interpreted
     |      as in slice notation.
     |  
     |  decode(self, /, encoding='utf-8', errors='strict')
     |      Decode the bytes using the codec registered for encoding.
     |      
     |      encoding
     |        The encoding with which to decode the bytes.
     |      errors
     |        The error handling scheme to use for the handling of decoding errors.
     |        The default is 'strict' meaning that decoding errors raise a
     |        UnicodeDecodeError. Other possible values are 'ignore' and 'replace'
     |        as well as any other name registered with codecs.register_error that
     |        can handle UnicodeDecodeErrors.
     |  
     |  endswith(...)
     |      B.endswith(suffix[, start[, end]]) -> bool
     |      
     |      Return True if B ends with the specified suffix, False otherwise.
     |      With optional start, test B beginning at that position.
     |      With optional end, stop comparing B at that position.
     |      suffix can also be a tuple of bytes to try.
     |  
     |  expandtabs(...)
     |      B.expandtabs(tabsize=8) -> copy of B
     |      
     |      Return a copy of B where all tab characters are expanded using spaces.
     |      If tabsize is not given, a tab size of 8 characters is assumed.
     |  
     |  find(...)
     |      B.find(sub[, start[, end]]) -> int
     |      
     |      Return the lowest index in B where subsection sub is found,
     |      such that sub is contained within B[start,end].  Optional
     |      arguments start and end are interpreted as in slice notation.
     |      
     |      Return -1 on failure.
     |  
     |  hex(...)
     |      B.hex() -> string
     |      
     |      Create a string of hexadecimal numbers from a bytes object.
     |      Example: b'\xb9\x01\xef'.hex() -> 'b901ef'.
     |  
     |  index(...)
     |      B.index(sub[, start[, end]]) -> int
     |      
     |      Return the lowest index in B where subsection sub is found,
     |      such that sub is contained within B[start,end].  Optional
     |      arguments start and end are interpreted as in slice notation.
     |      
     |      Raises ValueError when the subsection is not found.
     |  
     |  isalnum(...)
     |      B.isalnum() -> bool
     |      
     |      Return True if all characters in B are alphanumeric
     |      and there is at least one character in B, False otherwise.
     |  
     |  isalpha(...)
     |      B.isalpha() -> bool
     |      
     |      Return True if all characters in B are alphabetic
     |      and there is at least one character in B, False otherwise.
     |  
     |  isascii(...)
     |      B.isascii() -> bool
     |      
     |      Return True if B is empty or all characters in B are ASCII,
     |      False otherwise.
     |  
     |  isdigit(...)
     |      B.isdigit() -> bool
     |      
     |      Return True if all characters in B are digits
     |      and there is at least one character in B, False otherwise.
     |  
     |  islower(...)
     |      B.islower() -> bool
     |      
     |      Return True if all cased characters in B are lowercase and there is
     |      at least one cased character in B, False otherwise.
     |  
     |  isspace(...)
     |      B.isspace() -> bool
     |      
     |      Return True if all characters in B are whitespace
     |      and there is at least one character in B, False otherwise.
     |  
     |  istitle(...)
     |      B.istitle() -> bool
     |      
     |      Return True if B is a titlecased string and there is at least one
     |      character in B, i.e. uppercase characters may only follow uncased
     |      characters and lowercase characters only cased ones. Return False
     |      otherwise.
     |  
     |  isupper(...)
     |      B.isupper() -> bool
     |      
     |      Return True if all cased characters in B are uppercase and there is
     |      at least one cased character in B, False otherwise.
     |  
     |  join(self, iterable_of_bytes, /)
     |      Concatenate any number of bytes objects.
     |      
     |      The bytes whose method is called is inserted in between each pair.
     |      
     |      The result is returned as a new bytes object.
     |      
     |      Example: b'.'.join([b'ab', b'pq', b'rs']) -> b'ab.pq.rs'.
     |  
     |  ljust(...)
     |      B.ljust(width[, fillchar]) -> copy of B
     |      
     |      Return B left justified in a string of length width. Padding is
     |      done using the specified fill character (default is a space).
     |  
     |  lower(...)
     |      B.lower() -> copy of B
     |      
     |      Return a copy of B with all ASCII characters converted to lowercase.
     |  
     |  lstrip(self, bytes=None, /)
     |      Strip leading bytes contained in the argument.
     |      
     |      If the argument is omitted or None, strip leading  ASCII whitespace.
     |  
     |  partition(self, sep, /)
     |      Partition the bytes into three parts using the given separator.
     |      
     |      This will search for the separator sep in the bytes. If the separator is found,
     |      returns a 3-tuple containing the part before the separator, the separator
     |      itself, and the part after it.
     |      
     |      If the separator is not found, returns a 3-tuple containing the original bytes
     |      object and two empty bytes objects.
     |  
     |  replace(self, old, new, count=-1, /)
     |      Return a copy with all occurrences of substring old replaced by new.
     |      
     |        count
     |          Maximum number of occurrences to replace.
     |          -1 (the default value) means replace all occurrences.
     |      
     |      If the optional argument count is given, only the first count occurrences are
     |      replaced.
     |  
     |  rfind(...)
     |      B.rfind(sub[, start[, end]]) -> int
     |      
     |      Return the highest index in B where subsection sub is found,
     |      such that sub is contained within B[start,end].  Optional
     |      arguments start and end are interpreted as in slice notation.
     |      
     |      Return -1 on failure.
     |  
     |  rindex(...)
     |      B.rindex(sub[, start[, end]]) -> int
     |      
     |      Return the highest index in B where subsection sub is found,
     |      such that sub is contained within B[start,end].  Optional
     |      arguments start and end are interpreted as in slice notation.
     |      
     |      Raise ValueError when the subsection is not found.
     |  
     |  rjust(...)
     |      B.rjust(width[, fillchar]) -> copy of B
     |      
     |      Return B right justified in a string of length width. Padding is
     |      done using the specified fill character (default is a space)
     |  
     |  rpartition(self, sep, /)
     |      Partition the bytes into three parts using the given separator.
     |      
     |      This will search for the separator sep in the bytes, starting at the end. If
     |      the separator is found, returns a 3-tuple containing the part before the
     |      separator, the separator itself, and the part after it.
     |      
     |      If the separator is not found, returns a 3-tuple containing two empty bytes
     |      objects and the original bytes object.
     |  
     |  rsplit(self, /, sep=None, maxsplit=-1)
     |      Return a list of the sections in the bytes, using sep as the delimiter.
     |      
     |        sep
     |          The delimiter according which to split the bytes.
     |          None (the default value) means split on ASCII whitespace characters
     |          (space, tab, return, newline, formfeed, vertical tab).
     |        maxsplit
     |          Maximum number of splits to do.
     |          -1 (the default value) means no limit.
     |      
     |      Splitting is done starting at the end of the bytes and working to the front.
     |  
     |  rstrip(self, bytes=None, /)
     |      Strip trailing bytes contained in the argument.
     |      
     |      If the argument is omitted or None, strip trailing ASCII whitespace.
     |  
     |  split(self, /, sep=None, maxsplit=-1)
     |      Return a list of the sections in the bytes, using sep as the delimiter.
     |      
     |      sep
     |        The delimiter according which to split the bytes.
     |        None (the default value) means split on ASCII whitespace characters
     |        (space, tab, return, newline, formfeed, vertical tab).
     |      maxsplit
     |        Maximum number of splits to do.
     |        -1 (the default value) means no limit.
     |  
     |  splitlines(self, /, keepends=False)
     |      Return a list of the lines in the bytes, breaking at line boundaries.
     |      
     |      Line breaks are not included in the resulting list unless keepends is given and
     |      true.
     |  
     |  startswith(...)
     |      B.startswith(prefix[, start[, end]]) -> bool
     |      
     |      Return True if B starts with the specified prefix, False otherwise.
     |      With optional start, test B beginning at that position.
     |      With optional end, stop comparing B at that position.
     |      prefix can also be a tuple of bytes to try.
     |  
     |  strip(self, bytes=None, /)
     |      Strip leading and trailing bytes contained in the argument.
     |      
     |      If the argument is omitted or None, strip leading and trailing ASCII whitespace.
     |  
     |  swapcase(...)
     |      B.swapcase() -> copy of B
     |      
     |      Return a copy of B with uppercase ASCII characters converted
     |      to lowercase ASCII and vice versa.
     |  
     |  title(...)
     |      B.title() -> copy of B
     |      
     |      Return a titlecased version of B, i.e. ASCII words start with uppercase
     |      characters, all remaining cased characters have lowercase.
     |  
     |  translate(self, table, /, delete=b'')
     |      Return a copy with each character mapped by the given translation table.
     |      
     |        table
     |          Translation table, which must be a bytes object of length 256.
     |      
     |      All characters occurring in the optional argument delete are removed.
     |      The remaining characters are mapped through the given translation table.
     |  
     |  upper(...)
     |      B.upper() -> copy of B
     |      
     |      Return a copy of B with all ASCII characters converted to uppercase.
     |  
     |  zfill(...)
     |      B.zfill(width) -> copy of B
     |      
     |      Pad a numeric string B with zeros on the left, to fill a field
     |      of the specified width.  B is never truncated.
     |  
     |  ----------------------------------------------------------------------
     |  Class methods defined here:
     |  
     |  fromhex(string, /) from builtins.type
     |      Create a bytes object from a string of hexadecimal numbers.
     |      
     |      Spaces between two numbers are accepted.
     |      Example: bytes.fromhex('B9 01EF') -> b'\\xb9\\x01\\xef'.
     |  
     |  ----------------------------------------------------------------------
     |  Static methods defined here:
     |  
     |  __new__(*args, **kwargs) from builtins.type
     |      Create and return a new object.  See help(type) for accurate signature.
     |  
     |  maketrans(frm, to, /)
     |      Return a translation table useable for the bytes or bytearray translate method.
     |      
     |      The returned table will be one where each byte in frm is mapped to the byte at
     |      the same position in to.
     |      
     |      The bytes objects frm and to must be of the same length.
    
    

返回一个新的二进制序列 bytes 对象。参数可以是：
- 0~255 的整数组成的可迭代类型
- 字符串，并指定编码格式 encoding
- 与缓冲区接口一致的对象
- 整数
- 或者不传参数


```python
type(bytes)
```




    type




```python
bytes([1,2,3])
```




    b'\x01\x02\x03'




```python
bytes('嗨', 'utf-8')
```




    b'\xe5\x97\xa8'




```python
bytes(3)
```




    b'\x00\x00\x00'




```python
bytes()
```




    b''


