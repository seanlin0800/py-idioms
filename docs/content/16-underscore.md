# 用 `_` 代表未使用的變數

當使用回傳 tuple 的函式時，有時候不是每一個值都需要用到，這時我們習慣上使用 `_` 作為暫時變數的名稱。不過你的程式如果須支援 i18n ，慣例上也是用 `_` 當 gettext 的簡寫，例如在 Django 通常是這麼寫的:

```python
from django.db import models
from django.utils.translation import ugettext_lazy as _


class MyThing(models.Model):
    name = models.CharField(help_text=_('This is the help text'))
```

這時就會跟我們的 `_` 有衝突，所以有需要的話可改用 `__` 來解決這個問題。

慣用

```python
filename = 'foobar.txt'
basename, _, ext = filename.rpartition('.')
```

非慣用

```python
filename = 'foobar.txt'
basename, tmp, ext = filename.rpartition('.')
```

也可在 iteration 使用

```python
for _ in range(10):
    print 'Hello World!'
```
