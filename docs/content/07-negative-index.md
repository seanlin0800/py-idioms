# 負數索引值

Python 的 index 可以是負數，這對許多人來說是比較不習慣的特性。例如想得到字串的最後一個字

慣用

```python
word[-1]
```

非慣用

```python
word_len = len(word)
word[word_len - 1]
```

也可以用於 slicing ，以下程式傳回帳號末四碼

慣用

```python
def get_check_number(account):
    return account[-4:]
```

非慣用

```python
def get_check_number(account):
    account_len = len(account)
    return account[account_len - 4:]
```
