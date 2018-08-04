# Convenience Imports

許多時候 `__init__.py` 是空白的檔案，初學者可能覺得它沒什麼用處，就只是 Python 規定 packages 要有這個檔案。如果我們的 package 有一大堆 modules 時，這時它就有用了。

我們可以在 `__init__.py` 裡頭 import 物件進來，這樣想使用那些 modules 的人就只要 import 該 init module（用 package 的名稱）就可以了。 Python 許多 frameworks 都大量運用 convenience imports，例如 Djanogo:

- `django/views/generic/__init__.py`

```python
from django.views.generic.base import View, TemplateView, RedirectView
from django.views.generic.dates import (ArchiveIndexView, YearArchiveView, MonthArchiveView,
                                        WeekArchiveView, DayArchiveView, TodayArchiveView,
                                        DateDetailView)
from django.views.generic.detail import DetailView
from django.views.generic.edit import FormView, CreateView, UpdateView, DeleteView
from django.views.generic.list import ListView
```

這樣我們就可以不用管那些 XXView 到底是在哪個 module 裡，我們只要知道 generic 就好。

慣用

```python
from django.views import generic
# generic.FormView, generic.ListView
```

非慣用

```python
from django.views.generic.edit import FormView
from django.views.generic.list import ListView
```
