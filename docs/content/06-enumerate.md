# 善用 `enumerate`

從其他語言陣營來的人可能很習慣對陣列這麼操作:

```c++
for (int i = 0; i < a.size(); i++)
{
    // print i, a[i] ...
}
```

也就是直接拿個變數當 index 來操作，在 Python 中如果需要用到 index 的話，可使用內建函式 `enumerate`

慣用

```python
names = ['Alice', 'Bob', 'Cindy']
for index, element in enumerate(names):
    print '%d %s' % (index, element)
```

非慣用

```python
names = ['Alice', 'Bob', 'Cindy']
index = 0
while index < len(names):
    print '%d %s' % (index, names[index])
    index += 1
```
