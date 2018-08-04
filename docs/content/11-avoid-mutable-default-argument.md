# 避免用 mutable 預設引數

[Python tutorial](https://docs.python.org/2/tutorial/controlflow.html#default-argument-values)
> **Important warning**: The default value is evaluated only once. This makes a difference when the default is a mutable object such as a list, dictionary, or instances of most classes.

會有什麼風險請參閱 Python tutorial 裡面的例子，常用的解決方式是使用 None 當預設引數。

慣用

```python
def f(a, L=None):
    if L is None:
        L = []
    L.append(a)
    return L
```

有風險

```python
def f(a, L=[]):
    L.append(a)
    return L
```

注意這並不是 Python 的 bug，而是它的一種特性，Python 裡頭凡事皆物件，所以函式也不例外。函式有個 attribute 叫做 `__defaults__` 拿來存放預設引數，你可以做個小實驗，印出上面的 `f.__defaults__`，結果會是一個 1-tuple，裡面放的是一個 list。

我們可以利用此一特性來做 memoization，例如用 DP 求 Fibonacci number:

```python
def fib(n, memo={}):
    if n < 2:
        return 1
    if n not in memo:
        memo[n] = fib(n-1) + fib(n-2)
    return memo[n]
```
