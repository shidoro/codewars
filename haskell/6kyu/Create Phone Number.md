# Description

Write a function that accepts an array of 10 integers (between 0 and 9), that returns a string of those numbers in the form of a phone number.

**Example**:

```hs
createPhoneNumber [1,2,3,4,5,6,7,8,9,0] -- => returns "(123) 456-7890"
```

The returned format must be correct in order to complete this challenge.
Don't forget the space after the closing parentheses!

---

## Solution

```hs
module CreatePhoneNumber where

import Text.Printf (printf)

createPhoneNumber :: [Int] -> String
createPhoneNumber [a, b, c, d, e, f, g, h, i, l] = printf "(%d%d%d) %d%d%d-%d%d%d%d" a b c d e f g h i l
```
