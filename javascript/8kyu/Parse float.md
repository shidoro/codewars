# Description

Write function `parseF` which takes an input and returns a number or null if conversion is not possible. The input can be one of many different types so be aware.

---

## Solution

```js
const parseF = (s) => ((f) => (isNaN(f) ? null : f))(parseFloat(s));
```
