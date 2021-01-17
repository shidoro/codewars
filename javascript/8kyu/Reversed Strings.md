# Description

Complete the solution so that it reverses the string passed into it.

```
'world'  =>  'dlrow'
```

---

## Solution

```js
const solution = (s) => [...s].map(Array.prototype.pop, [...s]).join``;
```
