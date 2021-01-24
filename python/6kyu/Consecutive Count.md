# Description

I want to know the size of the longest consecutive elements of X in Y. You will receive two arguments: `items` and `key`. Return the length of the longest segment of consecutive `keys` in the given `items`.

**Notes**:

- The items and the key will be either an integer or a string
- If the key does not appear in the items, return 0

**Examples**

```
90000, 0           -->  4
"abcdaaadse", "a"  -->  3
"abcdaaadse", "z"  -->  0
```

---

## Solution

```py
from re import findall

def get_consective_items(items, key):
    return len((findall(rf"({key}+)(?!.*\1)", str(items)) or [''])[0])
```
