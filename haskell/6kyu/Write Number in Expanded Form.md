# Description

**Write Number in Expanded Form**

You will be given a number and you will need to return it as a string in Expanded Form. For example:

```
expandedForm(12); // Should return '10 + 2'
expandedForm(42); // Should return '40 + 2'
expandedForm(70304); // Should return '70000 + 300 + 4'
```

NOTE: All numbers will be whole numbers greater than 0.

---

## Solution

```hs
module Kata where

import Data.Char (digitToInt)
import Data.List (intercalate)

expandedForm :: Int -> String
expandedForm n = intercalate " + " . words . res . show $ n where
  res :: String -> String
  res [] = []
  res (x:xs) = if x /= '0' then show (digitToInt x * 10 ^ (length xs)) ++ " " ++ res xs else res xs
```
