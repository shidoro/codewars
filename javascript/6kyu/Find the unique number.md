# Description

There is an array with some numbers. All numbers are equal except for one. Try to find it!

```js
findUniq([1, 1, 1, 2, 1, 1]) === 2;
findUniq([0, 0, 0.55, 0, 0]) === 0.55;
```

It’s guaranteed that array contains at least 3 numbers.

The tests contain some very huge arrays, so think about performance.

---

## Solution

```js
const findUniq = (arr) =>
  +Object.entries(
    arr.reduce((acc, v) => ((acc[v] = ++acc[v] || 1), acc), {})
  ).sort((a, b) => a[1] - b[1])[0][0];
```
