# Generator Expressions

之前提到的 **list comprehensions** 是很強大的東西，但有時我們並不需要用到一個完整的 list，這時就可使用 **generator expressions**。

**Generator expressions** 跟 **list comprehensions** 結構很像，只差在它是以 `()` 包起來，而不是 `[]`。簡單講就是 generator 版的 **list comprehensions**，不同之處在於它不會建立 list ，而是 generator 物件。如此一來好處就是節省記憶體空間，尤其是你要處理的數量很巨大時。

如果 **generator expressions** 做為函式唯一參數時，可以省掉括號，但其他情況下括號不可省略。

```python
# http://legacy.python.org/dev/peps/pep-0289/
sum(x**2 for x in range(10))
reduce(operator.add, (x**2 for x in range(10)))
g = (x**2 for x in range(10))
```

下面的程式碼來自 [A Nice Little Bit of Python](http://www.jeffknupp.com/blog/2014/05/28/a-nice-little-bit-of-python/)，用途是檢查字串是否有特定的結尾。

慣用

```python
if any(needle.endswith(e) for e in ('ly', 'ed', 'ing', 'ers')):
    print('Is valid')
else:
    print('Invalid')
```

非慣用

```python
if any([needle.endswith(e) for e in ('ly', 'ed', 'ing', 'ers')]):
    print('Is valid')
else:
    print('Invalid')
```
