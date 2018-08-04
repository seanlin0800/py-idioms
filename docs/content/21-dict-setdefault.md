# dict.setdefault()

```python
dict.setdefault(key, default=None)
```

`dict.setdefault()` 和 `dict.get()` 類似，但不一樣的地方在於，如果 key 不在該 dictionary 中，就會設 `dict[key] = default`，然後回傳 default ，如果 key 存在的話，就回傳 `dict[key]`。

善用 `dict.setdefault()` 可以幫助我們簡化程式，下面的例子中使用它可以省掉判斷 key 存不存在的程式碼。

慣用

```python
the_dict = {}
for author, book in books:
    the_dict.setdefault(author, []).append(book)
```

非慣用

```python
the_dict = {}
for author, book in books:
    if author not in the_dict:
        the_dict[author] = []
    the_dict[author].append(book)
```
