# Description

Some numbers have funny properties. For example:

> _89 --> 8¹ + 9² = 89 \* 1_

> _695 --> 6² + 9³ + 5⁴= 1390 = 695 \* 2_

> _46288 --> 4³ + 6⁴+ 2⁵ + 8⁶ + 8⁷ = 2360688 = 46288 \* 51_

Given a positive integer n written as abcd... (a, b, c, d... being digits) and a positive integer p

- we want to find a positive integer k, if it exists, such as the sum of the digits of n taken to the successive powers of p is equal to k \* n.
  In other words:

> _Is there an integer k such as : (a ^ p + b ^ (p+1) + c ^(p+2) + d ^ (p+3) + ...) = n \* k_

If it is the case we will return k, if not return -1.

**Note**: n and p will always be given as strictly positive integers.

```hs
digpow 89 1 should return 1 since 8¹ + 9² = 89 = 89 * 1
digpow 92 1 should return -1 since there is no k such as 9¹ + 2² equals 92 * k
digpow 695 2 should return 2 since 6² + 9³ + 5⁴= 1390 = 695 * 2
digpow 46288 3 should return 51 since 4³ + 6⁴+ 2⁵ + 8⁶ + 8⁷ = 2360688 = 46288 * 51
```

---

## Solution

```hs
module Codewars.Kata.DigPow where

import Data.Char (digitToInt)

digpow :: Int -> Int -> Int
digpow n p = if rem x n == 0 then div x n else -1 where
  x = snd . foldl (\(i, acc) x -> (i + 1, acc + digitToInt x ^ i)) (p, 0) . show $ n
```
