# Description

You have an array of numbers.
Your task is to sort ascending odd numbers but even numbers must be on their places.

Zero isn't an odd number and you don't need to move it. If you have an empty array, you need to return it.

_Example_

```py
sortArray([5, 3, 2, 8, 1, 4]) == [1, 3, 2, 8, 5, 4];
```

---

## Solution

```py
def sort_array(source_array):
    s = sorted(filter(lambda x: x % 2, source_array), reverse = True)
    return [*map(lambda x: x if not x % 2 else s.pop(), source_array)]
```
