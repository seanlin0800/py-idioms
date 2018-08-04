# 儘量別用 `from module import *`

Python 初學者很常見的錯誤是為了貪圖方便而濫用 `from module import *` ，但這是很不好的寫法，PEP 8 建議避免使用。缺點有：

- 汙染 namespace ，可能覆蓋掉原先存在的物件
- 不方便閱讀程式碼，因為不知道該物件來自哪個 module

儘管如此，在實際開發上還是看得到 `from module import *` ，例如寫 Django 的人習慣在 `settings.py` 底下加上

```python
try:
    from local.local_settings import *
except ImportError:
    LOG.warning("No local_settings file found.")
```

將自訂的設定寫在 `local_settings.py` 裡頭，然後藉由 `import *` 覆蓋掉 `settings.py` 預設的東西。
