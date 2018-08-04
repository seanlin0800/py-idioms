# 請愛用 `in`

## If Statements

你覺得哪種寫法較清楚呢？

慣用

```python
if name in ('Alice', 'Bob', 'Charlie'):
    print 'ok'
```

非慣用

```python
if name == 'Alice' or name == 'Bob' or name == 'Charlie':
    print 'ok'
```

## 替代 `find()`

如果只是想知道某字串是否包含特定字串

慣用

```python
msg = 'Hello world!'
if 'world' in msg:
    print 'find it' 
```

非慣用

```python
msg = 'Hello world!'
if msg.find('world') != -1:
    print 'find it' 
```
