# Description

Code a function which will return an array with all prime numbers smaller than or equal to an arbitrary parameter "n".

Assume that all parameters will be numbers.

Remember that in some test cases with a big enough "n", performance might be (more) important.

---

## Solution

```js
const primeArray = (n) => {
  const checkPrime = (p) => {
    if (p < 2) return false;
    for (let i = 2; i < p; i++) if (!(p % i)) return false;
    return true;
  };
  return Array.from({ length: n }, (_, i) => ++i).reduce(
    (acc, v) => (checkPrime(v) ? acc.push(v) : acc, acc),
    []
  );
};
```
