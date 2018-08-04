# 別用 implicit relative imports

Python 3 已經移除了 **implicit relative imports**，在 2.7 雖然還是可以用，但為了避免麻煩，請務必使用 **absolute imports** 或者 **explicit relative imports**。

有的風格指南，例如 [Google Python Style Guide](https://github.com/google/styleguide/blob/gh-pages/pyguide.md#22-imports) ，建議只用 **absolute imports**，我想是因為歷史因素，因為 Python 2.5 以前沒有 **explicit relative imports**。

假設我們的檔案結構如下

```
animals/
      __init__.py
      cats/
              __init__.py
              base.py
              domestic_cats.py
      dogs/
              __init__.py
              base.py
              street_dogs.py
```

慣用

- `dogs/street_dogs.py`

```python
from animals.dogs import base
```

```python
from . import base
```

不要用

- `dogs/street_dogs.py`

```python
import base
```

跨 package 的 import 較常見的是使用 **absolute imports**

- `dogs/street_dogs.py`

```python
from animals.cats import domestic_cats
```
