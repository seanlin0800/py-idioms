# `collections.defaultdict`

在 [Python 慣用語 - 21](http://seanlin.logdown.com/posts/238476-python-idioms-21-dictsetdefault) 我們提到 `dict.setdefault()` 的用法，但有可讀性更高的做法，但不是使用內建的 `dict` ，而是 `collections` 裡的 `defaultdict`。

`defaultdict` 是在 Python 2.5 正式加入的，所以較早期的程式碼看不到它的身影，我們來看一下怎麼達到 [Python 慣用語 - 21](http://seanlin.logdown.com/posts/238476-python-idioms-21-dictsetdefault) 的程式:

```python
import collections

the_dict = collections.defaultdict(list)
for author, book in books:
    the_dict[author].append(book)
```

`defaultdict` 的第一個引數是一個 factory function ，用來替 `defaultdict` 實例裡頭不存在的 key 設定 value 預設值，這上面的例子中為 list ，所以每個預設值為 `list()`，也就是 `[]`。

`defaultdict` 其餘的用法和 `dict` 是一樣的，因為是 `dict` 的子類。
