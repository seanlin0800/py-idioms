# import 的順序

當我們的程式所依賴的 modules 越來越多時，將它們分類可以幫助我們很快看出來用到那些 modules。 PEP 8 建議的 import 語句順序如下：

```
{{ Python 內建的 modules }}
\n
{{ 第三方 modules }}
\n
{{ 本地 modules }}
```

實際的例子（取自 [OpenStack Horizon](https://github.com/openstack/horizon)）：

```python
import json
import logging

from django.core import urlresolvers
from django import shortcuts
from django import template
from django.utils.translation import ugettext_lazy as _

from horizon import conf
from horizon import exceptions
from horizon import messages
from horizon import tables
from horizon.templatetags import sizeformat
from horizon.utils import filters
```
OpenStack 建議按照 modules 路徑的字母順去排序，不過許多開源計畫並沒有這麼要求。
