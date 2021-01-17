# Description

Complete the solution so that the function will break up camel casing, using a space between words.

**Example**

```
solution("camelCasing")  ==  "camel Casing"
```

---

## Solution

```hs
module Codewars.Kata.BreakCamelCase where

import Data.Char (isUpper)

solution :: String -> String
solution (x : xs) = x : res xs where
  res :: String -> String
  res [] = []
  res (x : xs) = if isUpper x then ' ' : x : res xs else  x : res xs
```
