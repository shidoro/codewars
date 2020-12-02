# Description

Jumping number is the number that All adjacent digits in it differ by 1.

**Task**

Given a number, Find if it is Jumping or not .

---

## Solution

```js
const jumpingNumber = (n, r = "") =>
  (() => (r ? r : "Jumping!!"))(
    [...String(n)].reduce((acc, v) =>
      Math.abs(+acc - +v) === 1 ? (acc = v) : (r = "Not!!")
    )
  );
```
