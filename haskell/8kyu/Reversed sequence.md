# Description

Build a function that returns an array of integers from n to 1 where `n>0`.

Example : n=5 >> [5,4,3,2,1]

---

## Solution

```hs
module RevSeq where
reverseSeq :: Int -> [Int]
reverseSeq n = [n, n - 1 .. 1]
```
