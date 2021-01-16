# Description

Complete the method/function so that it converts dash/underscore delimited words into camel casing. The first word within the output should be capitalized only if the original word was capitalized (known as Upper Camel Case, also often referred to as Pascal case).

**Examples**

```py
to_camel_case("the-stealth-warrior") # returns "theStealthWarrior"

to_camel_case("The_Stealth_Warrior") # returns "TheStealthWarrior"
```

---

## Solution

```py
from re import sub

def to_camel_case(text):
    return sub(r"[^a-zA-Z].", lambda x: x.group()[1].upper(), text)
```
