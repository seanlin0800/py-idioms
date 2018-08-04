# 請愛用 `dict.get()`

善用 `dict.get()` 的 default，可以幫助我們寫出更精巧且可讀性更好的程式。

慣用

```python
name = some_dict.get('name', 'Bob')
```

非慣用

```python
if 'name' in some_dict:
    name = some_dict['name']
else:
    name = 'Bob'
```

上面可以再進一步改成這樣:

```python
name = (some_dict['name'] if 'name' in some_dict else 'Bob')
```

但是不如 `dict.get()` 來得好。
