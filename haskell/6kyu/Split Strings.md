# Description

Complete the solution so that it splits the string into pairs of two characters. If the string contains an odd number of characters then it should replace the missing second character of the final pair with an underscore ('\_').

Examples:

```hs
solution "abc" `shouldBe` ["ab", "c_"]
solution "abcdef" `shouldBe` ["ab", "cd", "ef"]
```

---

## Solution

```hs
module Codewars.Kata.SplitStrings where

import Data.List.Split (chunk)

solution :: String -> [String]
solution st = if length st `mod` 2 == 0 then chunk 2 st else chunk 2 (st ++ "_")
```
