# Description

Your goal in this kata is to implement a difference function, which subtracts one list from another and returns the result.

It should remove all values from list `a`, which are present in list `b`.

```hs
difference [1,2] [1] == [2]
```

If a value is present in b, all of its occurrences must be removed from the other:

```hs
difference [1,2,2,2,3] [2] == [1,3]
```

---

## Solution

```hs
module Difference where

difference :: Eq a => [a] -> [a] -> [a]
difference a b = filter (not . flip elem b) a
```
