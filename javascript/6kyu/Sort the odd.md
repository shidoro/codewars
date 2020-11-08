# Description

You have an array of numbers.
Your task is to sort ascending odd numbers but even numbers must be on their places.

Zero isn't an odd number and you don't need to move it. If you have an empty array, you need to return it.

_Example_

```js
sortArray([5, 3, 2, 8, 1, 4]) == [1, 3, 2, 8, 5, 4];
```

---

## Solution

```js
const sortArray = (array) =>
  ((odd) =>
    array.reduce((acc, v) => (acc.push(v % 2 ? odd.shift() : v), acc), []))(
    array.filter((n) => n % 2).sort((a, b) => a - b)
  );
```
