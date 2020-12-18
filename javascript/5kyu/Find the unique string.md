# Description

There is an array of strings. All strings contains similar letters except one. Try to find it!

```js
findUniq(['Aa', 'aaa', 'aaaaa', 'BbBb', 'Aaaa', 'AaAaAa', 'a']) === 'BbBb';
findUniq(['abc', 'acb', 'bac', 'foo', 'bca', 'cab', 'cba']) === 'foo';
```

Strings may contain spaces. Spaces is not significant, only non-spaces symbols matters. E.g. string that contains only spaces is like empty string.

It’s guaranteed that array contains more than 3 strings.

---

## Solution

```js
const findUniq = (arr) =>
  ((xs, [a, b, c] = xs.slice(0, 3), reg = new RegExp(a || '^$')) =>
    a !== b && a !== c ? a : arr.filter((_, i) => !reg.test(xs[i]))[0])(
    arr.map((str) => [...new Set(str.toLowerCase())].sort().join(``))
  );
```
