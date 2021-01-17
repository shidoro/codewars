# Description

In mathematics, a [Diophantine equation](https://en.wikipedia.org/wiki/Diophantine_equation) is a polynomial equation, usually with two or more unknowns, such that only the integer solutions are sought or studied.

In this kata we want to find all integers x, y (x >= 0, y >= 0) solutions of a diophantine equation of the form:

**x2 - 4 \* y2 = n**

(where the unknowns are x and y, and n is a given positive number) in decreasing order of the positive xi.

If there is no solution return `[]` or `"[]"` or `""`. (See "RUN SAMPLE TESTS" for examples of returns).

**Examples**:

```
solEquaStr(90005) --> "[[45003, 22501], [9003, 4499], [981, 467], [309, 37]]"
solEquaStr(90002) --> "[]"
```

**Hint**:
x2 - 4 * y2 = (x - 2*y) * (x + 2*y)

---

## Solution

```hs
module Codewars.Kata.Dioph where

solequa :: Integer -> [(Integer, Integer)]
solequa n = [(div a 2, div b 4) | i <- [1..floor . sqrt . fromIntegral $ n], let (a, b) = (div n i + i, div n i - i), mod b 4 == 0 && mod n i == 0]
```
