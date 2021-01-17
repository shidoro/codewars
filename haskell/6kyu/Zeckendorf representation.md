# Description

Every positive integer can be written as a sum of [Fibonacci numbers](https://en.wikipedia.org/wiki/Fibonacci_number). For example `10 = 8 + 2 or 5 + 3 + 2 or 3 + 3 + 2 + 2`. Apparently, this representation is not unique.

It becomes unique, if we rule out _consecutive_ Fibonacci numbers: this is [Zeckendorf's theorem](https://en.wikipedia.org/wiki/Zeckendorf%27s_theorem), first proven by Lekkerkerker in 1952. In the example above, this excludes the last two representations (containing the consecutive Fibonacci numbers `2` and `3`), and we are left with the _Zeckendorf representation_ `10 = 8 + 2`.

Complete the function that returns the Zeckendorf representation of a given integer `n` as a list of Fibonacci numbers in decreasing order. Return an empty list for `n = 0` and `None/nil` for negative `n`.

_Hint: Be greedy!_

---

## Solution

```hs
module ZeckendorfRepresentation (zeckendorf) where

import Data.Maybe (fromJust)

zeckendorf :: Int -> Maybe [Int]
zeckendorf n
  | n < 0 = Nothing
  | n == 0 = Just []
  | otherwise = Just $ m : fromJust (zeckendorf (n - m)) where
    m = fib n 1 1

fib :: Int -> Int -> Int -> Int
fib n a b | b > n = a | otherwise = fib n b (a + b)
```
