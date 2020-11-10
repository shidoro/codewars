# Description

Your task is to remove all **consecutive duplicate** words from string, leaving only first words entries. For example:

```
"alpha beta beta gamma gamma gamma delta alpha beta beta gamma gamma gamma delta"

--> "alpha beta gamma delta alpha beta gamma delta"
```

---

## Solution

```py
import re
def remove_consecutive_duplicates(s):
    return re.sub(r"\b(\w+)(\s(\1\b))+", r"\1", s)
```
