# Description

Complete the method/function so that it converts dash/underscore delimited words into camel casing. The first word within the output should be capitalized only if the original word was capitalized (known as Upper Camel Case, also often referred to as Pascal case).

**Examples**

```hs
toCamelCase "the-stealth-warrior" -- returns "theStealthWarrior"

toCamelCase "The_Stealth_Warrior" -- returns "TheStealthWarrior"
```

---

## Solution

```hs
module CamelCase where

import Data.Char (isAlpha, toUpper)

toCamelCase :: String -> String
toCamelCase = foldr (\x acc -> if isAlpha x then x : acc else if null acc then acc else toUpper (head acc) : tail acc ) []
```
