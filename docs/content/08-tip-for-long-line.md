# 太長怎麼辦

PEP 8 訂出每行最多 79 個字元
> Limit all lines to a maximum of 79 characters.

雖然不少人對這有意見，有的是訂出 120 個字元，無論如何可讀性優先。舉個例子， SQL 字串有可能很長一大串，通通塞在同一行會嚴重影響可讀性，這時就須將字串分成多行。

慣用

```python
sql = (
    "SELECT name, product, price "
    "FROM production.product "
    "WHERE description = 'TEST' "
    "AND days < 10 "
    "ORDER BY name DESC"
)
```

非慣用

```python
sql = "SELECT name, product, price " \
      "FROM production.product " \
      "WHERE description = 'TEST' " \
      "AND days < 10 " \
      "ORDER BY name DESC"
```

使用括號來達到接續的作用是很常見且較好的作法，因為使用 `\` 不僅麻煩，而且很有可能不小心在後面多了空白字元，造成錯誤。

[Implicit line joining](https://docs.python.org/2/reference/lexical_analysis.html#implicit-line-joining)
