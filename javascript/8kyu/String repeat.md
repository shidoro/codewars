# Description

Write a function called `repeat_str` which repeats the given string `src` exactly `count` times.

```js
repeatStr(6, 'I'); // "IIIIII"
repeatStr(5, 'Hello'); // "HelloHelloHelloHelloHello"
```

---

## Solution

```js
const repeatStr = (n, s) => s.repeat(n);
```
