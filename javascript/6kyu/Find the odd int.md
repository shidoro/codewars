# Description

Given an array of integers, find the one that appears an odd number of times.

There will always be only one integer that appears an odd number of times.

---

## Solution

```js
const findOdd = (arr) => arr.reduce((acc, v) => acc ^ v, 0);
```
