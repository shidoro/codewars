# Description

Modify the `kebabize` function so that it converts a camel case string into a kebab case.

```py
kebabize('camelsHaveThreeHumps'); // camels-have-three-humps
kebabize('camelsHave3Humps'); // camels-have-humps
```

Notes:

- the returned string should only contain lowercase letters

---

## Solution

```py
from re import sub

def kebabize(string):
    return sub(r"(?<!\b)([A-Z])" , r"-\1" , sub(r"\d", "", string)).lower()
```
