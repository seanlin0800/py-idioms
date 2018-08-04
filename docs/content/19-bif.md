# 請愛用 BIFs

BIF 是 **Built-in Function** 的縮寫，Python 提供許多好用內建函數可以使用，沒事可以多多瀏覽下面的網頁，避免重造輪子。
https://docs.python.org/2/library/functions.html

這裡列出幾個例子

## `all()`

慣用

```python
def is_valid(file_names):
    return all('py' in name for name in file_names)
```

非慣用

```python
def is_valid(file_names):
    for name in file_names:
        if not 'py' in name:
            return False
    return True
```

## `any()`

慣用

```python
def is_dangerous(sql):
    actions = ('update', 'delete', 'replace')
    return any(sql.startswith(action) for action in actions)
```

非慣用

```python
def is_dangerous(sql):
    actions = ('update', 'delete', 'replace')
    for action in actions:
        if sql.startswith(action):
            return True
    return False
```

## `sum()`

慣用

```python
prices = [100, 300, 50, 600]
total = sum(prices)
```

非慣用

```python
prices = [100, 300, 50, 600]
total = 0
for price in prices:
    total += price
```
