# Description

There is an array with some numbers. All numbers are equal except for one. Try to find it!

```py
find_uniq([ 1, 1, 1, 2, 1, 1 ]) == 2
find_uniq([ 0, 0, 0.55, 0, 0 ]) == 0.55
```

It’s guaranteed that array contains at least 3 numbers.

The tests contain some very huge arrays, so think about performance.

---

## Solution

```py
def find_uniq(arr):
    a, b, c = arr[0], arr[1], arr[2]
    if a != b and a != c: return a
    for x in arr:
        if x != a: return x
```
