# Description

Write simple .camelCase method (`camel_case` function in PHP, `CamelCase` in C# or `camelCase` in Java) for strings. All words must have their first letter capitalized without spaces.

For instance:

```hs
camelCase("hello case"); // => "HelloCase"
camelCase("camel case word"); // => "CamelCaseWord"
```

Don't forget to rate this kata! Thanks :)

---

## Solution

```hs
module CamelCase.JorgeVS.Kata where

import Data.Char (toUpper)
import Data.List (intercalate)

camelCase :: String -> String
camelCase = intercalate "" . map ((:) . toUpper . head <*> tail) . words
```
