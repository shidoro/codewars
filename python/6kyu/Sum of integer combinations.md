# Description

Consider the array `[3,6,9,12]`. If we generate all the combinations with repetition that sum to `12`, we get `5` combinations: `[12], [6,6], [3,9], [3,3,6], [3,3,3,3]`. The length of the sub-arrays (such as `[3,3,3,3]` should be less than or equal to the length of the initial array (`[3,6,9,12]`).

Given an array of positive integers and a number `n`, count all combinations with repetition of integers that sum to `n`. For example:

```
find([3,6,9,12],12) = 5.
```

More examples in the test cases.

Good luck!

---

## Solution

```py
def find(arr,n,l = -1):
    if l < 0: l = len(arr)
    if n == 0: return 1
    if l == 0: return 0

    r = 0

    for i, m in enumerate(arr):
        r += find(arr[0 : i + 1], n - m, l - 1)

    return r
```
