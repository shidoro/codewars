# Description

Write a function that takes a number or a string and gives back the number of **permutations without repetitions** that can generated using all of its element.; more on permutations [here](https://en.wikipedia.org/wiki/Permutation).

For example, starting with:

```
1
45
115
"abc"
```

You could respectively generate:

```
1
45,54
115,151,511
"abc","acb","bac","bca","cab","cba"
```

So you should have, in turn:

```js
perms(1) == 1;
perms(45) == 2;
perms(115) == 3;
perms("abc") == 6;
```

---

## Solution

```js
const perms = (element) =>
  [...String(element)].reduce((acc, _, i) => (acc *= ++i), 1) /
  Object.values(
    [...String(element)].reduce((acc, v) => ((acc[v] = ++acc[v] || 1), acc), {})
  )
    .filter((n) => n !== 1)
    .reduce(
      (acc, v) => (
        (acc *= Array(v)
          .fill()
          .reduce((acc, _, i) => (acc *= ++i), 1)),
        acc
      ),
      1
    );
```
