# Description

There is an array with some numbers. All numbers are equal except for one. Try to find it!

```hs
getUnique [1, 1, 1, 2, 1, 1] -- Result is 2
getUnique [0, 0, 0.55, 0, 0] -- Result is 0.55
```

It’s guaranteed that array contains at least 3 numbers.

The tests contain some very huge arrays, so think about performance.

---

## Solution

```hs
module CodeWars.UniqueNumber where

getUnique :: [Int] -> Int
getUnique xxs@(x : y : z : xs)
  | x /= y && x /= z = x
  | otherwise = head $ filter (/= x) xxs
```
