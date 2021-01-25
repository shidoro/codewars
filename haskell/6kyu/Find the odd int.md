# Description

Given an array of integers, find the one that appears an odd number of times.

There will always be only one integer that appears an odd number of times.

---

## Solution

```hs
module Codewars.Kata.FindOdd where

import Data.Bits (xor)

findOdd :: [Int] -> Int
findOdd = foldr xor 0
```
