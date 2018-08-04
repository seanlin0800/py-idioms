# If Statements

這在 PEP 8 有提到，別和 `True` 以及 `False` 用 `==` 比較

慣用

```python
if valid():
    print 'valid'
if not valid():
    print 'invalid'
```

非慣用

```python
if valid() == True:
    print 'valid'
if valid() == False:
    print 'invalid'
```

對 sequences (strings, lists, tuples) 來說，因為空的 sequence 是 `False`，不需判斷長度是否為零。

慣用

```python
if not users:
    print 'No users available'
```

非慣用

```python
if len(users) == 0:
    print 'No users available'
```

對數值形態比較時需要明確地比值

```python
if i % 2 == 0:
    print 'even number'
```

非慣用

```python
if not i % 2:
    print 'even number'
```

和 `None` 比較要使用 `is` 和 `is not`，儘管在正常情況下和 `==` 沒有啥差別，但這已經是大家習慣的用法了，以下來自 PEP8。
> Comparisons to singletons like None should always be done with is or is not, never the equality operators.

在 [stackoverflow](http://stackoverflow.com/questions/14247373/python-none-comparison-should-i-use-is-or) 有人舉例

```python
class Negator(object):
    def __eq__(self, other):
        return not other

thing = Negator()
print thing == None    # True
print thing is None    # False
```
