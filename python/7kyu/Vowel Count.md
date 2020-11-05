# Description

Return the number (count) of vowels in the given string.
We will consider a, e, i, o, u as vowels for this Kata (but not y).
The input string will only consist of lower case letters and/or spaces.

---

## Solution

```py
import re
def get_count(str):
    return len(re.findall(r"[aeiou]", str))
```
