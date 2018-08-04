# Conditional Expressions

許多程式語言都有 **ternary operator** `?:` 這種東西，Python 並沒有這樣的 operator ，但有個慣用表達方式可以達到類似目的，不過要注意太複雜的語句就不適合這樣使用了。

慣用

```python
def foo(logging):
    level = (1 if logging else 0)
```

非慣用

```python
def foo(logging):
    if logging:
        level = 1
    else:
        level = 0
```

注意等號右邊使用括號括起來，這是比較[推薦的寫法](https://docs.python.org/2.5/whatsnew/pep-308.html)，不過許多程式都沒採用這樣的寫法。
