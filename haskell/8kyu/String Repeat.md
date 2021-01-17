# Description

Write a function called `repeat_str` which repeats the given string `src` exactly `count` times.

```hs
repeatStr(6, "I") // "IIIIII"
repeatStr(5, "Hello") // "HelloHelloHelloHelloHello"
```

---

## Solution

```hs
module StringRepeat where

repeatStr :: Int -> String -> String
repeatStr n = (>>) [1..n]
```
