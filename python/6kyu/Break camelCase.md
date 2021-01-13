# Description

Complete the solution so that the function will break up camel casing, using a space between words.

**Example**

```
solution("camelCasing")  ==  "camel Casing"
```

---

## Solution

```py
from re import sub

def solution(s):
    return sub(r"[A-Z]", " \g<0>", s)
```
