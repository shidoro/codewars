# Description

Given a number, return a string with dash `'-'` marks before and after each odd integer, but do not begin or end the string with a dash mark.

Ex:

```py
dashatize(274) -> '2-7-4'
dashatize(6815) -> '68-1-5'
```

---

## Solution

```py
import re

def dashatize(num):
    return '-'.join(re.findall(r"[13579]|[02468]+", str(num))) or "None"
```
