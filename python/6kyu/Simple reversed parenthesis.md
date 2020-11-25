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

```py
def solve(s):
    if len(s) & 1: return -1

    open, close = 0, 0

    for char in s:
        if char == '(':
            close += 1
        elif close:
            close -= 1
        else:
            open += 1
            close += 1

    return open + close / 2
```
