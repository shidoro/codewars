# Description

Given a string of digits, you should replace any digit below 5 with '0' and any digit 5 and above with '1'. Return the resulting string.

---

## Solution

```hs
module Codewars.Kata.FakeBinary where

fakeBin :: String -> String
fakeBin = foldr (\x acc -> if x < '5' then '0' : acc else '1' : acc) ""
```
