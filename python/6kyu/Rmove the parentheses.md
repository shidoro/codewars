# Description

**Remove the parentheses**

In this kata you are given a string for example:

```py
"example(unwanted thing)example";

```

Your task is to remove everything inside the parentheses as well as the parentheses themselves.

The example above would return:

```py
"exampleexample";

```

**Notes**

- Other than parentheses only letters and spaces can occur in the string. Don't worry about other brackets like `"[]"` and `"{}"` as these will never appear.
- There can be multiple parentheses.
- The parentheses can be nested.

---

## Solution

```py
import re
def remove_parentheses(s):
    return remove_parentheses(re.sub(r"\(([^\(]*?)\)", "", s)) if re.search(r"\(([^\(]*?)\)", s) else s
```
