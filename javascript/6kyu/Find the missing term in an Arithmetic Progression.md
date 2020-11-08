# Description

An Arithmetic Progression is defined as one in which there is a constant difference between the consecutive terms of a given series of numbers. You are provided with consecutive elements of an Arithmetic Progression. There is however one hitch: exactly one term from the original series is missing from the set of numbers which have been given to you. The rest of the given series is the same as the original AP. Find the missing term.

You have to write a function that receives a list, list size will always be at least 3 numbers. The missing term will never be the first or last one.

**Example**

```js
find_missing([1, 3, 5, 9, 11]) == 7;
```

---

## Solution

_maths_

```js
const findMissing = (list) =>
  ((list[0] + list[list.length - 1]) * (list.length + 1)) / 2 -
  list.reduce((acc, v) => acc + v, 0);
```

_don't dispare, you don't need to know maths to do it_

```js
const findMissing = (list) => {
  list = list.sort((a, b) => a - b);

  const diff = Math.min(list[1] - list[0], list[2] - list[1]);
  const set = new Set(list);
  const rangeSet = new Set();

  for (let i = list[0]; i <= list[list.length - 1]; i += diff) {
    rangeSet.add(i);
  }

  for (const key of rangeSet) {
    if (!set.has(key)) return key;
  }

  return list.length;
};
```
