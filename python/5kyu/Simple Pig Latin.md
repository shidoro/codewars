# Description

Move the first letter of each word to the end of it, then add "ay" to the end of the word. Leave punctuation marks untouched.

**Examples**

```py
pigIt('Pig latin is cool'); // igPay atinlay siay oolcay
pigIt('Hello world !'); // elloHay orldway !
```

---

## Solution

```py
from re import sub

def pig_it(text):
    return sub(r"\b(\w)(\w*)\b", r"\2\1ay", text)
```
