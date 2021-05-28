# Description

Substitute two equal letters by the next letter of the alphabet (two letters convert to one):

```
"aa" => "b", "bb" => "c", .. "zz" => "a".
```

The equal letters do not have to be adjacent.
Repeat this operation until there are no possible substitutions left.
Return a string.

Example:

```
let str = "zzzab"
    str = "azab"
    str = "bzb"
    str = "cz"
return "cz"
```

Notes

- The order of letters in the result is not important.
- The letters `"zz"` transform into `"a"`.
- There will only be lowercase letters.

---

## Solution

```py
from re import sub, search;

repl = lambda c: ord(c) == 122 and 'a' or chr(ord(c) + 1);

def last_survivors(string):
    if not search(r"(\w).*?\1", string): return string;
    return last_survivors(sub(r"(\w)(.*?)\1", lambda x: repl(x.group(1)) + x.group(2), string));
```
