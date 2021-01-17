# Description

## This code does not execute properly. Try to figure out why.

---

### Problem

```hs
module Multiply.Bug.Fix where

import System.IO.Unsafe (unsafePerformIO)

multiply :: Int -> Int -> Int
multiply a b = unsafePerformIO $ do
  return $ a * b
```

### Solution

```hs
module Multiply.Bug.Fix where

multiply :: Int -> Int -> Int
multiply = (*)
```
