# Chained Comparisons

Python 的比較運算子可以練接起來，這是許多語言沒有的特性，正常情況下可讓程式更符合實際上的意義，提高可讀性。

慣用

```python
if a < b < c <= d:
    return True
```

非慣用

```python
if a < b and b < c and c <= d:
    return True
```

不正常的情況就是濫用此一特性，寫出像這樣的東西

```python
if data == result is not None:
    return True
```
