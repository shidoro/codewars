# Description

Complete the square sum function so that it squares each number passed into it and then sums the results together.

For example, for `[1, 2, 2]` it should return `9` because `1^2 + 2^2 + 2^2 = 9`.

---

## Solution

```hs
module SquareSum where

squareSum :: [Integer] -> Integer
squareSum = sum . map (^2)
```
