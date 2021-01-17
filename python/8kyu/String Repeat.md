# Description

Write a function called `repeat_str` which repeats the given string `src` exactly `count` times.

```py
repeatStr(6, "I") // "IIIIII"
repeatStr(5, "Hello") // "HelloHelloHelloHelloHello"
```

---

## Solution

```py
def repeat_str(repeat, string):
    return string * repeat
```
