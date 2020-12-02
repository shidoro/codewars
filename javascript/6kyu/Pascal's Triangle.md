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

```js
const pascalsTriangle = (n) => {
  if (n === 1) return [1];
  const xs = [[1], [1, 1]];

  for (let i = 2; i < n; i++) {
    xs.push([1]);
    for (let j = 0, l = xs[xs.length - 2].length - 1; j < l; j++)
      xs[xs.length - 1].push(xs[xs.length - 2][j] + xs[xs.length - 2][j + 1]);

    xs[xs.length - 1].push(1);
  }

  return xs.reduce((acc, v) => acc.concat(v), []);
};
```
