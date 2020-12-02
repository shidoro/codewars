# Description

In mathematics, Pascal's triangle is a triangular array of the binomial coefficients expressed with formula `(n k) = n!/(n-k)!`, where `n` denotes a row of the triangle, and `k` is a position of a term in the row.

You can read [Wikipedia article on Pascal's Triangle](https://en.wikipedia.org/wiki/Pascal's_triangle) for more information.

**Task**

Write a function that, given a depth `n`, returns `n` top rows of Pascal's Triangle flattened into a one-dimensional list/array.

`n` guarantees that terms of the Triangle won't overflow.

**Example**:

```
n = 1: [1]
n = 2: [1,  1, 1]
n = 4: [1,  1, 1,  1, 2, 1,  1, 3, 3, 1]
```

---

## Solution

```py
def pascals_triangle(n):
    xs, k = [], 0

    for i in range(n):
        k = len(xs) - i
        for j in range(i + 1):
            if j == 0 or j == i: xs.append(1)
            else: xs.append(xs[k + j] + xs[k + j - 1])

    return xs
```
