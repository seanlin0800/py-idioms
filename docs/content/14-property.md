# 用 `property` 取代 getters 與 setters

寫 Java 的人習慣寫一堆 getX() 以及 setX()，這在 Python 中是不被鼓勵的，pythonic 方式是直接存取 attribute ，而當你需要進一步控制時，可以使用 `property` 達到 getter 以及 setter 效果，如此一來，客戶端的程式不需要修改就能正常運作。

Python 的 threading.Thread 在 2.6 以前只有 getName() 、 setName() 等深受 Java 影響的 methods，後來開始提供 `property` 的版本了。

慣用

```python
class Egg(object):

    def __init__(self, price):
        self._price = price

    @property
    def price(self):
        return self._price * RATE
    
    @price.setter
    def price(self, value):
        self._price = value
```

非慣用

```python
class Egg(object):

    def __init__(self, price):
        self._price = price

    def get_price(self):
        return self._price * RATE

    def set_price(self, value):
        self._price = value
```

要避免對吃資源的 method 使用 `property` ，因為存取 attribute 給人的感覺是很輕量的操作，這樣使用該物件的人就有可能忽視效能的問題。
