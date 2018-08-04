# 用 `join()` 生成字串

當你要從一個 list 裡頭的一堆字串串接起來時，Python 有個高效率且可讀性高的做法。

慣用

```python
name_list = ['Alice', 'Bob', 'Cindy']
name_formatted = ', '.join(name_list)
```

非慣用

```python
name_list = ['Alice', 'Bob', 'Cindy']
name_formatted = name_list[0]
for name in name_list[1:]:
    name_formatted += ', ' + name
```
