# Description

Given an array of integers, find the one that appears an odd number of times.

There will always be only one integer that appears an odd number of times.

---

## Solution

```py
from functools import reduce

def find_it(seq):
    return reduce(lambda x, y: x ^ y, seq)
```
