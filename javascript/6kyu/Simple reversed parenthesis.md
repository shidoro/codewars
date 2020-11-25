# Description

Given a string, return the minimal number of parenthesis reversals needed to make balanced parenthesis.

For example:

```
solve(")(") = 2 Because we need to reverse ")" to "(" and "(" to ")". These are 2 reversals.
solve("(((())") = 1 We need to reverse just one "(" parenthesis to make it balanced.
solve("(((") = -1 Not possible to form balanced parenthesis. Return -1.
```

Parenthesis will be either `"("` or `")"`.

More examples in the test cases.

Good luck.

---

## Solution

```js
function solve(s) {
  if (s.length % 2) return -1;

  let open = 0,
    close = 0;

  for (const char of s)
    char === "(" ? close++ : close ? close-- : (open++, close++);

  return open + close / 2;
}
```
