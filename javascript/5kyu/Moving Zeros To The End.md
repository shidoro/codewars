# Description

Write an algorithm that takes an array and moves all of the zeros to the end, preserving the order of the other elements.

```js
moveZeros([false, 1, 0, 1, 2, 0, 1, 3, 'a']); // returns[false,1,1,2,1,3,"a",0,0]
```

---

## Solution

```js
const moveZeros = (arr) => (
  (z = []),
  (r = arr.filter((v) => (v !== 0 ? true : (z.push(v), false)))),
  r.concat(z)
);
```
