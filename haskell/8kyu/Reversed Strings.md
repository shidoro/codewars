# Description

Complete the solution so that it reverses the string passed into it.

```
'world'  =>  'dlrow'
```

---

## Solution

```hs
module Solution where

solution :: String -> String
solution = foldl (flip (:)) []
```
