# Description

In this Kata, you will sort elements in an array by decreasing frequency of elements. If two elements have the same frequency, sort them by increasing value.

```js
solve([2,3,5,3,7,9,5,3,7]) = [3,3,3,5,5,7,7,2,9]
--we sort by highest frequency to lowest frequency. If two elements have same frequency, we sort by increasing value
```

More examples in test cases.

Good luck!

---

## Solution

```js
const curry = (fn, arity = fn.length) =>
  (nextCurried = (prevArgs) => (...nextArgs) => (
    (args = [...prevArgs, ...nextArgs]),
    args.length < arity ? nextCurried(args) : fn(...args)
  ))([]);

const reduce = curry((fn, initial, arr) => arr.reduce(fn, initial));
const sort = curry((fn, arr) => arr.sort(fn));
const map = curry((fn, arr) => arr.map(fn));

const count = (arr) =>
  reduce((acc, v) => ((acc[v] = ++acc[v] || 1), acc), {}, arr);

const entries = (arr) => Object.entries(arr);
const freqSort = (arr) => sort(([k, m], [p, n]) => n - m || k - p, arr);
const extend = (arr) => map(([m, n]) => Array(n).fill(+m), arr);
const flat = (arr) => reduce((acc, v) => acc.concat(v), [], arr);
const pipe = (...fns) =>
  fns.reduce((fn1, fn2) => (...args) => fn2(fn1(...args)));

const solve = ([...arr]) => pipe(count, entries, freqSort, extend, flat)(arr);
```
