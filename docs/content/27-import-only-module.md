# 儘量少用 `from module import obj`

[Google Python Style Guide](https://google-styleguide.googlecode.com/svn/trunk/pyguide.html#Imports) 以及 [OpenStack Style Guidelines](http://docs.openstack.org/developer/hacking/#imports) 建議只能 import modules，其優點有：

- 閱讀程式碼時不必查詢就能知道該函式或類別來自哪個 module
- 避免 import 進來的物件名稱產生衝突
- 避免 import 進來一大堆東西
- 一致性，import 就來的只有 module

當然這不是強制性的規則，除了上述兩種指南外，其餘多數指南並無此規則，但我覺得應視為一種寫程式的好習慣。

慣用

```python
from django import forms
# forms.CharField, forms.DateTimeField ....
```

少用

```python
from django.forms import (
    CharField, DateTimeField, EmailField,
    ChoiceField, IPAddressField)
```
