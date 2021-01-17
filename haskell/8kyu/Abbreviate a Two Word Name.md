# Description

Write a function to convert a name into initials. This kata strictly takes two words with one space in between them.

The output should be two capital letters with a dot separating them.

It should look like this:

`Sam Harris` => `S.H`

`Patrick Feeney` => `P.F`

---

## Solution

```hs
module Initials where

import Data.Char (toUpper)
import Data.List (intersperse)

getInitials :: String -> String
getInitials = intersperse '.' . map (toUpper . head) . words
```
