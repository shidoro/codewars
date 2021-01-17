# Description

Given a string of digits, you should replace any digit below 5 with '0' and any digit 5 and above with '1'. Return the resulting string.

---

## Solution

```py
def fake_bin(x):
    return ''.join(str(0) if int(n) < 5 else str(1) for n in x);
```
