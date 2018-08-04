# Context Managers

**context managers** 可供 `with/as` 使用，保證某些動作一定能執行，可取代 `try/finally`，讓你省掉一些麻煩，許多地方都可以看到它的存在。

經典的例子就是對檔案的操作:

慣用

```python
with open('tmp.txt', 'w') as f:
    f.write('TEST')
```

非慣用

```python
f = open('tmp.txt', 'w')
try:
    f.write('TEST')
finally:
    f.close()
```

除了 file objects，`threading` 裡頭有[好幾個物件](https://docs.python.org/2/library/threading.html#using-locks-conditions-and-semaphores-in-the-with-statement)也提供這樣的操作。假設你操作的物件不是 **context manager**，那麼記得使用 `try/finally` 來確保資源被釋放掉。

實現 **context managers** 有兩種方式，一種是有 `__enter__` 以及 `__exit__` 的 class ，另一種方式是 generator function 搭配 decorator `contextlib.contextmanager`。詳情請看 http://pymotw.com/2/contextlib/
