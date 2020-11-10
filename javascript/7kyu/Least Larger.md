# Description

**Task**

Given an array of numbers and an index, return the index of the least number larger than the element at the given index, or -1 if there is no such index ( or, where applicable, Nothing or a similarly empty value ).

**Notes**

Multiple correct answers may be possible. In this case, return any one of them.
The given index will be inside the given array.
The given array will, therefore, never be empty.

**Example**

```js
leastLarger( [4, 1, 3, 5, 6], 0 )  =>  3
leastLarger( [4, 1, 3, 5, 6], 4 )  => -1
```

---

## Solution

```js
const leastLarger = (a, i) => a.indexOf(Math.min(...a.filter((n) => n > a[i])));
```
