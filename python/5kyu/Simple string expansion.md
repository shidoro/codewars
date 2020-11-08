# Description

Consider the following expansion:

```py
solve("3(ab)") = "ababab"     -- because "ab" repeats 3 times
solve("2(a3(b))" = "abbbabbb" -- because "a3(b)" == "abbb", which repeats twice.
```

Given a string, return the expansion of that string.

Input will consist of only lowercase letters and numbers (1 to 9) in valid parenthesis. There will be no letters or numbers after the last closing parenthesis.

More examples in test cases.

Good luck!

---

## Solution

```py
import re
def solve(st):
    return st if not re.search(r"(\d)?\((\w*)\)", st) else solve(re.sub(r"(\d)?\((\w*)\)", lambda x: x.group(2) * (1 if not x.group(1) else int(x.group(1))) ,st))
```
