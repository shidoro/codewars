# Description

Given a number, return a string with dash `'-'` marks before and after each odd integer, but do not begin or end the string with a dash mark.

Ex:

```js
dashatize(274) -> '2-7-4'
dashatize(6815) -> '68-1-5'
```

---

## Solution

```js
const dashatize = (num) =>
  (num.toString().match(/([13579]|[02468]+)/g, "$1") || []).join("-") || "NaN";
```
