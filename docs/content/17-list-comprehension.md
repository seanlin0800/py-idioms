# List Comprehensions

Python 2.7 以後有三種 comprehensions，在此之前只有 **list comprehensions**
* list comprehensions
* dictionary comprehensions
* set comprehensions

其中 **list comprehensions** 是最常見到的，使用時機是當你需要從 iterable 製造出另一個 list 時，適當地使用可以讓程式碼更清楚，而且比起 `map()` 以及 `filter()` 來得更簡單且有彈性。所謂的「適當地使用」要看你所處的團隊怎麼定義，例如 [Google Python style guide](https://github.com/google/styleguide/blob/gh-pages/pyguide.md#27-comprehensions--generator-expressions) 不建議使用多個 for 和 filter expressions。

慣用

```python
import glob
import os

imgs = [
    f.upper()
    for f in glob.iglob('*.gif')
    if os.stat(f).st_size > 2000
]
```

非慣用

```python
import glob
import os

imgs = []
for f in glob.iglob('*.gif'):
    if os.stat(f).st_size > 2000:
        imgs.append(f.upper())
```

也可使用 `filter()` 和 `map()`，但可讀性比較差。

```python
import glob
import os

imgs = map(
	lambda x: x.upper(),
    filter(lambda f: os.stat(f).st_size > 2000, glob.iglob('*.gif')
)
```
