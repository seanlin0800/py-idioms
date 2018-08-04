# loop 也可以有 else

Python 中 for 以及 while loop 可以像 if 一樣有個 else 區塊，當迴圈沒有中斷就會執行到 else 區塊。
[Python tutorial](https://docs.python.org/2/tutorial/controlflow.html#break-and-continue-statements-and-else-clauses-on-loops):
> Loop statements may have an else clause; it is executed when the loop terminates through exhaustion of the list (with for) or when the condition becomes false (with while), but not when the loop is terminated by a break statement.

這乍看之下沒有甚麼用，但在一些情況下是有好處的，可以取代大家常用的 flag 這種暫時性的變數，讓程式的意圖更為明顯。

```python
for n in range(2, 10):
    for x in range(2, n):
        if n % x == 0:
            print n, 'equals', x, '*', n/x
            break
    else:
        print n, 'is a prime number'
```

可以取代下面的寫法

```python
for n in range(2, 10):
    is_prime = True
    for x in range(2, n):
        if n % x == 0:
            print n, 'equals', x, '*', n/x
            is_prime = False
            break
    if is_prime:
        print n, 'is a prime number'
```
