# Description

Make a function that will return a greeting statement that uses an input; your program should return, `"Hello, <name> how are you doing today?"`.

SQL: return results in a column named `greeting`

_[Make sure you type the exact thing I wrote or the program may not execute properly]_

---

## Solution

```hs
module Greeting where

greeting :: String -> String
greeting name = (++) "Hello, " name ++ " how are you doing today?"
```
