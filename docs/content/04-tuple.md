# Tuple 的妙用

## Tuple Packing/Unpacking

tuple packing/unpacking 是什麼呢？

```python
t = 12345, 54321, 'hello!'
x, y, z = t
```

第一個是 **tuple packing** ，等號右邊被打包成 `tuple` ，第二個是 **tuple unpacking** ，就是反過來，其實不只 `tuple` 可這樣用，詳情請看 [Python tutorial](https://docs.python.org/2/tutorial/datastructures.html#tuples-and-sequences) 的說明。

## Multiple Assignment

慣用

```python
my_list = ['Alice', 12, 'Python']
(name, age, skill) = my_list
```

非慣用

```python
my_list = ['Alice', 12, 'Python']
name = my_list[0]
age = my_list[1]
skill = my_list[2]
```

## Swap

在其他語言，例如 C，要交換兩個變數通常是使用第三個變數 temp ，對數值型態的話有不同的[邪惡技巧](http://www.programmingsimplified.com/c-program-swap-two-numbers)，但可讀性不佳。在 Python 利用 `tuple`可達成目的，而且不需要暫時變數。

慣用

```python
(x, y) = (y, x)
```

非慣用

```python
temp = x
x = y
y = temp
```

## 回傳多值

`tuple` 還有其他應用，知道 Python 函式怎麼回傳多值嗎？

```python
def get_error_details():
    return (2, 'details')


(errnum, errstr) = get_error_details()
```
